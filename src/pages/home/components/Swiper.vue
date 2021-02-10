<template>
  <div class="wrapper">
  <swiper :options="swiperOptions">
    <swiper-slide v-for="item of swiperList" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl">
    </swiper-slide>
    <div class="swiper-pagination" slot="pagination"></div>
  </swiper></div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data( ) {
      return {
        swiperOptions: {
            pagination: '.swiper-pagination',
            loop: true
        },
        swiperList: [{
            id: '0001',
            imgUrl: "https://imgs.qunarzz.com/vs_ceph_vcimg/569cae4ae98e9793f7341e85eed73c54.jpeg"
        }, {
            id: '0002',
            imgUrl: "https://imgs.qunarzz.com/vs_ceph_vcimg/f03f5ac90ae59d0d9c6332a2bfd9782e.jpeg"
        }]
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