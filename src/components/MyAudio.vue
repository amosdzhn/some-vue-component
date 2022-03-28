<template>
<div>
  <audio
      id="myaudio"
      :src="audioSrc"
      controls="controls"
      preload="auto"
  >

  </audio>
</div>
</template>

<script>
export default {
  name: "MyAudio",
  props:{
    initAudioSrc:{
      type: String,
      required: true,
    }
  },
  data: function (){
    return {
      audioSrc: this.initAudioSrc,
    }
  }
}
</script>

<style scoped>

</style>