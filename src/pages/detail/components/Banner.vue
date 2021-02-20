<template>
  <div>
  <div class="banner" @click="handleBannerClick">
      <img class="banner-img" :src="bannerImg">
      <div class="banner-info">
          <div class="banner-tittle">{{this.sightName}}</div>
          <div class="banner-number"><span class="iconfont">&#xe692;</span>
          {{this.bannerImgs.length}}</div>
      </div>
      </div>
      <fade-animation>
        <common-gallary :imgs="bannerImgs" v-show="showGallary"
        @close="handleGallaryClose"></common-gallary>
      </fade-animation>

  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary.vue'
import FadeAnimation from 'common/fade/FadeAnimation.vue'
export default {
  name:'DetailBanner',
  props:{
    sightName:String,
    bannerImg:String,
    bannerImgs:Array
  },
  data() {
    return{
      showGallary: false,
    }
  },
  components: {CommonGallary,FadeAnimation},
  methods: {
    handleBannerClick() {
      this.showGallary = true
    },
    handleGallaryClose() {
      this.showGallary= false
    }
  }
    
}
</script>

<style lang="stylus" scoped>
    .banner
        position relative
        overflow hidden
        height: 0
        padding-bottom :55%
        .banner-img
            width: 100%
        .banner-info
            display flex
            position absolute
            left 0
            right 0
            bottom 0
            line-height .6rem
            color #fff
            background-image linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,0.8))
          .banner-tittle
            flex 1
            font-size .32rem
            padding 0  .4rem
          .banner-number
            padding 0 .28rem
            margin-top .14rem
            height .4rem
            line-height .4rem
            border-radius .2rem
            background rgba(0,0,0,0.8)
            font-size .24rem
          .iconfont
            font-size .24rem
            margin-right .1rem
</style>