<template>
  <div class="wrapper">
  <swiper :options="swiperOptions" v-if="showSwiper">
    <swiper-slide v-for="item of List" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl">
    </swiper-slide>
    <div class="swiper-pagination" slot="pagination"></div>
  </swiper></div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  props: {
    List: Array
  },
  data( ) {
      return {
        swiperOptions: {
            pagination: '.swiper-pagination',
            loop: true
        }
    }
  },
  computed: {
    showSwiper () {
      return this.List.length
    }
  }
}
</script>

<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background: #fff
  .wrapper
    overflow hidden
    width: 100%
    height: 0
    padding-bottom: 30.5%
    background: #eee
  .swiper-img
    width: 100%
</style>