<!-- system.vue-->
<template>
      <section>
         <div class="color_con" :style="{background:color}" @click="handleShowColor"></div>
              <div v-show="colorShow">
              <sketch-picker v-model="tableData.color" @input="updateValue"></sketch-picker>
         </div>
     </section>
</template>
<script>
import { Sketch } from 'vue-color'
export default {
  name: 'system',
  components: {
    'sketch-picker': Sketch
  },
  data () {
    return {
      color: #000;
      // 颜色选择器
      colorShow: false,
      colors: {
        hex: '#194d33',
        hsl: { h: 150, s: 0.5, l: 0.2, a: 1 },
        hsv: { h: 150, s: 0.66, v: 0.30, a: 1 },
        rgba: { r: 25, g: 77, b: 51, a: 1 },
        a: 1
      }
    }
  },
  methods:{
   // 颜色选择器
    handleShowColor () {
      if (this.colorShow) {
        this.colorShow = false
      } else {
        this.colorShow = true
      }
    },
    updateValue (val) {
      console.log('颜色选择', val) // 输出参数如下图1-1
      this.color = val.hex
    },
  }
</script>
