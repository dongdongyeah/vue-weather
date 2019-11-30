<template>
  <div class='home'>
    <home-header></home-header>
    <real-time></real-time>
  </div>
</template>

<script>
import HomeHeader from '@/pages/Home/components/Header'
import RealTime from '@/pages/Home/components/RealTime'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    RealTime
  }
}
</script>

<style lang='stylus' scoped>
.home
  background: rgb(137, 196, 244)
  color: #fff
</style>
