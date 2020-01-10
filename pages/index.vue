<template>
  <div class="container">
      <youtube :video-id="videoId" :player-vars="playerVars" @ready="ready" @playing="playing"></youtube>
  </div>
</template>

<script>
export default {
  data() {
    return {
      videoId : "CGp1-4EovDk",
      playerVars : {
        // start: 10,
        autoplay: 1
      }
    }
  },

  methods: {
      ready (event) {
        this.player = event.target;

        setInterval(() => {
          this.player.seekTo(100, true);
        }, 5000)

        // this.player.seekTo(100, true);
      }
  }

}
</script>

<style>

</style>
