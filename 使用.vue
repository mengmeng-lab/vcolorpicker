<!--system.vue-->
<template>
      <colorPicker v-model="color" @change="handleChangeColor"></colorPicker>
</template>
<script>

export default {
  name: 'system',
  data () {
    return {
      color: #000;
    }
  },
  methods:{
   handleChangeColor (val) {
      console.log('输出颜色值',val)  // 颜色 #6c8198
   },
  }
</script>
