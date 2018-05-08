<template>
  <div>
    <home></home>
    <router-view></router-view>
  </div>
</template>

<script>
import home from '@/components/home'
export default {
  data () {
    return {}
  },
  components: {
    home
  }
}
</script>

<style scoped>
html,
body {
  margin: 0;
  padding: 0;
}
</style>
