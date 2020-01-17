<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-md-12">
        
        {{ nowPlaying.comment }}
        <div class="movie-wrap">
          <youtube :video-id="nowPlaying.videoId" :player-vars="{ autoplay: 1 }" @ready="ready" @playing="playing"></youtube>
        </div>

        <button v-on:click="changeVideo">change</button>

      </div>

    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      nowPlaying:{
        videoId : "CGp1-4EovDk",
        comment : "ここすき",
        start : 5,
        end : 20
      }

    }
  },

  methods: {
      ready (event) {
        this.player = event.target;

        // ループ処理　再生時間を舐めて終了時間になったらシークバーを戻す
        setInterval(() => {
          if (this.player.getCurrentTime() >= this.nowPlaying.end) {
            this.player.seekTo(this.nowPlaying.start, true);
          }
        }, 100)

      },

      playing() {
        console.log(this.player.getCurrentTime())

        // 初回のみシークバー移動（指定しないと無限ループする）
        // この方法ではユーザ手動でシークバー変更が出来ない
        if (this.player.getCurrentTime() < 1) {
          this.player.seekTo(this.nowPlaying.start, true);
        }
        console.log("playing")

      },


      // 動画変更のサンプル
      changeVideo() {
        this.nowPlaying = {
          videoId : "_a9gUjJY-f4",
          comment : "これすき",
          start : 30,
          end : 40
        }

      },



  }

}
</script>

<style>
  .movie-wrap {
      position: relative;
      padding-bottom: 56.25%;
      height: 0;
      overflow: hidden;
  }
  
  .movie-wrap iframe {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
  }

</style>
