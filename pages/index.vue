<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-md-8">

        <div class="movie-wrap">
          <youtube :video-id="videoId" :player-vars="playerVars" @ready="ready" @playing="playing"></youtube>
        </div>

      </div>

      <div class="col-md-4">
        <div class="suko-card-margin">        
          <a class="suko-card-link" href="">
            <b-card  title="かわいそう" sub-title="220万の財布無くして、イジメられて、生きていく。【ヒカキン】">
              <b-card-text></b-card-text>
            </b-card>
          </a>
        </div>

        <div class="suko-card-margin">        
          <a class="suko-card-link" href="">
            <b-card  title="かわいそう" sub-title="220万の財布無くして、イジメられて、生きていく。【ヒカキン】">
              <b-card-text></b-card-text>
            </b-card>
          </a>
        </div>

        <div class="suko-card-margin">        
          <a class="suko-card-link" href="">
            <b-card  title="かわいそう" sub-title="220万の財布無くして、イジメられて、生きていく。【ヒカキン】">
              <b-card-text></b-card-text>
            </b-card>
          </a>
        </div>

      </div>

    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      videoId : "CGp1-4EovDk",
      playerVars : {
        // start: 10,
        autoplay: 0
      }
    }
  },

  methods: {
      ready (event) {
        this.player = event.target;

        // setInterval(() => {
        //   this.player.seekTo(100, true);
        // }, 5000)

        // this.player.seekTo(100, true);
      }
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

  .suko-card-link {
    text-decoration:none;
  }

  .suko-card-margin {
    margin-bottom: 10px;
  }
</style>
