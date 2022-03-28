<template>
<div>
  <!-- canvas是一个矩形画布，使用JS API生成图像。底层是一个个像素，
       canvas用于JS API 生成图像
       SVG用XML生成图像
  -->
  <canvas
      ref="myCanvas"
      :width="width"
      :height="height"
  >
    您的浏览器不支持canvas
  </canvas>
  <button @click="showHandler">显示图像</button>
</div>
</template>

<script>
export default {
  name: "MyCanvas",
  data: function (){
    return {
      width: 400,
      height: 300,
    }
  },
  methods:{
    showHandler(){
      let canvas = this.$refs.myCanvas
      let ctx = canvas.getContext('2d')
      ctx.fillStyle ='red'
      ctx.fillRect(0,0,400,300)
    }
  }
}
</script>

<style scoped>
canvas{
  border: 5px solid blue;
}

</style>