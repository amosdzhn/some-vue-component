<template>
<div>
  <h1>演示我的: 视频，音频，canvas组件</h1>
  <h3>视频</h3>
  <MyVideo
      :init-video-width="300"
      :init-video-height="200"
      :init-video-src="videoLoop"
      :init-video-poster="poster"></MyVideo>
  <hr/>
  <h3>音频</h3>
  <MyAudio :init-audio-src="audioSrc"></MyAudio>
  <hr/>
  <h3>canvas</h3>
  <MyCanvas></MyCanvas>
  <hr/>

</div>
</template>

<script>

import MyVideo from "@/components/MyVideo";
import MyAudio from "@/components/MyAudio";
import MyCanvas from "@/components/MyCanvas";

export default {
  name: "VideoCanvasAudio",
  components:{
    MyVideo,
    MyAudio,
    MyCanvas,
  },
  data:function (){
    return{
      videoLoop:[
          'http://www.amosdzhn.space:9000/sharefile/%E7%BE%8E%E5%A5%B31.mp4',
          'http://www.amosdzhn.space:9000/sharefile/%E7%BE%8E%E5%A5%B32.mp4',
      ],
      poster: 'http://www.amosdzhn.space:9000/sharefile/index.jpg',

      audioSrc: 'http://www.amosdzhn.space:9000/sharefile/%E6%B8%A9%E5%A5%95%E5%BF%83%20-%20%E4%B8%80%E8%B7%AF%E7%94%9F%E8%8A%B1.flac',
    }
  }
}
</script>

<style scoped>
h1 {
  text-align: center;
}
</style>