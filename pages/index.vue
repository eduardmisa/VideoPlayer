<template>
  <div class="d-flex responsive-video">
    <div class="d-flex flex-column ma-auto">
      <video controls width="500" height="500" ref="player">
        <source src="https://s3-ap-southeast-1.amazonaws.com/emisa.me/IMG_1149.MOV">
        Your browser does not support the video tag.
      </video>
      <v-btn x-large tile @click="Fullscreen">Fullscreen</v-btn>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    Fullscreen () {
      const app = this
      var elem = app.$refs.player
      if (elem.requestFullscreen) {
        elem.requestFullscreen();
      } else if (elem.mozRequestFullScreen) { /* Firefox */
        elem.mozRequestFullScreen();
      } else if (elem.webkitRequestFullscreen) { /* Chrome, Safari and Opera */
        elem.webkitRequestFullscreen();
      } else if (elem.msRequestFullscreen) { /* IE/Edge */
        elem.msRequestFullscreen();
      }
    }
  }
}
</script>

<style scoped>
.responsive-video {
  height: 100vh!important;
}
</style>