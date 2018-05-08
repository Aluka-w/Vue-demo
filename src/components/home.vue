<template>
 <div>
  <div class="father">
    <h2>实现父子组件传值: {{ word }}</h2>
    <input type="text" class="btn" v-model="word">
    <subHome :num="word" @changeNum="changeFatherNum"></subHome>
  </div>
 </div>
</template>
<script >
import subHome from './subHome.vue'
import Bus from '../../common/bus.js'
export default {
  data () {
    return {
      word: 6
    }
  },
  watch: {
    'word': function (val) {
      Bus.$emit('myWord', val)
    }
  },
  methods: {
    changeFatherNum (val) {
      this.word = val
    }
  },
  components: {
    subHome
  }
}
</script>

<style scoped>
  body,html {
    margin: 0;
    padding: 0;
  }
  .father {
    width: 400px;
    height: 400px;
    border: 1px solid teal;
    margin: 100px auto;
  }
  .btn {
    margin: 20px 0;
    line-height: 30px;
  }
</style>
