<template>
  <div>
    <home-Header></home-Header>
    <home-Swiper></home-Swiper>
    <home-icons></home-icons>
    <home-recommend></home-recommend>
    <home-weekend></home-weekend>
  </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons  from './components/Icons'
import HomeRecommend from './components/Recommend.vue'
import HomeWeekend from './components/Weekend.vue'

export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeWeekend
  }
}
</script>

<style>

</style>
