<template>
  <div class='home'>
    <home-header></home-header>
    <real-time></real-time>
    <today></today>
    <forecast></forecast>
    <living-index></living-index>
  </div>
</template>

<script>
import HomeHeader from '@/pages/Home/components/Header'
import RealTime from '@/pages/Home/components/RealTime'
import Today from '@/pages/Home/components/Today'
import Forecast from '@/pages/Home/components/Forecast'
import LivingIndex from '@/pages/Home/components/LivingIndex'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    RealTime,
    Today,
    Forecast,
    LivingIndex
  }
}
</script>

<style lang='stylus' scoped>
.home
  background: rgb(137, 196, 244)
  color: #fff
</style>
