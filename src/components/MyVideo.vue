<template>
  <div>
    <video
        id="myvideo"
        ref="myAudio"
        :poster="videoPoster"
        :src="videoSrc[0]"
        controls="controls"
        :width="videoWidth"
        :height="videoHeight"
        @ended="changeVideo()"
        @pause="pauseHandler()"
        @volumechange="volumechangeHandler()"
        @canplay="canplayHandler()"
        @emptied="emptiedHandler()"
        @loadeddata="loadeddataHandler()"
    >
      您的浏览器不支持video
    </video>
  </div>
</template>

<script>
export default {
  name: "MyVideo",
  props:{
    initVideoPoster:{
      type: String,
      required: false,
    },
    initVideoSrc: {
      type: Array,
      required: false,
      default: function(){return ['http://www.amosdzhn.space:9000/sharefile/%E7%BE%8E%E5%A5%B31.mp4']},
    },
    initVideoWidth:{
      type: Number,
      required: false,
      default: 600,
    },
    initVideoHeight:{
      type: Number,
      required: false,
      default: 400,
    }
  },
  data: function (){
    return {
      videoPoster: this.initVideoPoster,
      videoSrc: this.initVideoSrc,
      currentVideoIndex: 0,
      videoWidth: this.initVideoWidth,
      videoHeight: this.initVideoHeight,
    }
  },
  methods:{
    changeVideo(){
      //TODO
      //实现自动播放一下个
      // console.log("播放完毕")
      // console.log(this.videoSrc)
      // this.currentVideoIndex++
      // if( this.currentVideoIndex === (this.videoSrc.length -1) ){
      //   this.currentVideoIndex = 0
      // }
      // this.videoSrc = this.videoSrc[this.currentVideoIndex]
      // this.$nextTick(res => {
      //   console.log(res)
      //   this.$refs.myAudio.load()
      //   this.$refs.myAudio.play()
      // })

    },
    pauseHandler(){
      console.log("暂停了")
    },
    volumechangeHandler(){
      console.log("改变了音量")
    },
    canplayHandler(){
      console.log("媒介能够开始播放但可能因缓冲而需要停止时运行脚本")
    },
    emptiedHandler(){
      console.log("媒介资源元素突然为空时（网络错误、加载错误等）运行脚本")
    },
    loadeddataHandler(){
      console.log('加载媒介数据时运行脚本')
    }
  }
}
</script>

<style scoped>
/*
    样式定义: id选择器 (#id) 类选择器(.class)   选择器 { field:value;filed2:value2;}
            #div1,.c1,#div2{} <--- 这种定义方式为分组选择器,即多个元素使用同样的样式
            div #div1{}  <---- 嵌套选择器，表示 div 标签内部的 id为div1 的样式
    盒子模型: 每个元素的宽和高的设置，只是该元素内容的宽高。从内往外还有：padding,border,margin
        1.border:
          1.样式  border-style:dotted(点线边框),solid(实线边框),none(无边框),double(两个边框)
                               dashed(虚线边框),groove(3D沟槽边框，取决边框颜色值,)....
                               可单独指定 border-top-style:solid;
          2.颜色: border-color: 所有边框(left/top/right/bottom),也可以单独指定 border-left-color: red;
          3.宽度: border-width:所有边框(该是边框的宽度，不会影响包住的内容),也可以单独指定 border-top-width:30px;
          4.可以简写方式: border-color: red yellow blue green  (上，右，下，左),border-style ,border-width 都可以简写
                        border:5px solid red  (所有边框是 width=5px,style=solid,color=red)
          5.注意：border 的css只影响border,不会改变content的宽和高。
          6.总结: border -> width style color
         2.outline:
              outline 位于 border之外，也可设置 width style color
         3.margin:
              margin 位于 outline之外,可以单独设置margin-top margin-left等。
              可以设置为 auto，依赖于浏览器。具体的px,或者百分比%
              支持简写,margin: x x x x   上 右 下 左
                     margin: x y z    上x 左右y 下z
                     margin: x y      上下x, 左右y
                     margin: x        上 右 下 左 均x
         4.padding:
              padding 位于 content 与 border 之间，与 margin 类似,可以单独设置padding-top,padding-left等
              同样支持简写方式

*/
#myvideo {
  border: 20px solid rgba(211, 195, 227, 0.99);
  outline: 20px solid #a2e1e3;
  margin: auto;
  padding: 5px 15px;
  width: 50%;
}

hr{
  border: 5px solid black;
}
</style>
<!--
    显示Display与Visibility:
        display属性置为node,可以隐藏元素，且元素的布局也会移除
        visibility属性置为hidden,可以隐藏元素，但元素的布局不会被移除

    position(定位):
-->