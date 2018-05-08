<template>
  <div>
    <h1>实现非父子组件的传值</h1>
    <input type="text" class="worsd" v-model="word">
  </div>
</template>

<script>
import Bus from '../../common/bus.js'
export default {
  data () {
    return {
      word: 4
    }
  },
  created () {
    let _this = this
    Bus.$on('myWord', function (val) {
      _this.word = val
    })
  }
}
</script>

<style scoped>
html,
body {
  margin: 0;
  padding: 0;
}
.word {
  margin-top: 20px;
  height: 30px;
}
.super {
  display: block;
}
</style>
