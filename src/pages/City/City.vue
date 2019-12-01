<template>
  <div>
    <city-header></city-header>
    <city-list></city-list>
    <search-list></search-list>
  </div>
</template>

<script>
import CityHeader from '@/pages/City/components/Header'
import CityList from '@/pages/City/components/List'
import SearchList from '@/pages/City/components/SearchList'
export default {
  name: 'City',
  components: {
    CityHeader,
    CityList,
    SearchList
  }
}
</script>

<style lang='stylus' scoped>

</style>
