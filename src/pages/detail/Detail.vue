<template>
<div>
   <detail-banner></detail-banner>  
   <detail-header></detail-header>
   <div class="content"></div>
</div>
</template>

<script>
import DetailHeader from './components/Header.vue'
import DetailBanner from './components/Banner.vue'

export default {
    name:'Detail',
  components: { DetailBanner, DetailHeader },

}
</script>

<style lang="stylus" scoped>
  .content
    height: 50rem
    
</style>