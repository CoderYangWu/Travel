<template>
  <div>
    <home-Header :city="city"></home-Header>
    <home-Swiper :List="swiperList"></home-Swiper>
    <home-icons :List="iconList"></home-icons>
    <home-recommend :List="recommendList"></home-recommend>
    <home-weekend :List="weekendList"></home-weekend>
  </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons  from './components/Icons'
import HomeRecommend from './components/Recommend.vue'
import HomeWeekend from './components/Weekend.vue'
import axios from 'axios'

export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeWeekend
  },
  data () {
    return {
      city: '',
      swiperList :[],
      iconList :[],
      recommendList :[],
      weekendList :[]
    }
  },
  methods: {
    getHomeInfo () {
      axios.get('/api/index.json')
        .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      res=res.data
      if (res.ret && res.data) {
        const data = res.data
        this.city = data.city
        this.swiperList = data.swiperList
        this.iconList = data.iconList
        this.recommendList = data.recommendList
        this.weekendList = data.weekendList
      }
    }
  },
  mounted () {
    this.getHomeInfo()
  },
}
</script>

<style>

</style>
