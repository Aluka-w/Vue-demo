<template>
  <div>
    <div class="reduce" @click="reduceNum">-</div>
    <input type="text" @change="numChange" ref="numRef" class="num" v-model="word">
    <div class="add" @click="addNum">+</div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      word: 2
    }
  },
  props: ['num'],
  created () {
    this.word = this.num
  },
  watch: {
    'num': function (val) {
      this.word = val
    }
  },
  methods: {
    reduceNum () {
      this.word--
      this.justify()
    },
    addNum () {
      this.word++
      this.justify()
    },
    numChange () {
      this.word = this.$refs.numRef.value
      this.justify()
    },
    justify () {
      this.$emit('changeNum', this.word)
    }
  }
}
</script>

<style scoped>
  html,
  body {
    margin: 0;
    padding: 0;
  }
  .reduce,
  .add {
    width: 50px;
    height: 50px;
    border: 1px solid #345;
    display: inline-block;
    text-align: center;
    line-height: 50px;
    box-sizing: border-box;
    cursor: pointer;
  }
  .num {
    width: 50px;
    height: 50px;
    display: inline-block;
    text-align: center;
    line-height: 50px;
    box-sizing: border-box;
    border: 1px solid #345;
    position: relative;
    top: -2px;
  }
  </style>
