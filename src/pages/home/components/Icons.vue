<template>
    <div class="icons">
        <swiper>
        <swiper-slide v-for="(page,index) of pages"  :key="index">
            <div class="icon" v-for="item of page" :key="item.id">
            <div class="icon-img">
            <img class="icon-img-content" :src="item.imgUrl" alt="">
            </div>
            <p class="icon-desc">{{item.desc}}</p>
        </div>
        </swiper-slide>
        </swiper>
    </div>
        
</template>

<script>
export default {
    name: 'HomeIcons',
    data() {
        return {
            iconsList: [
                {
                    id:'0001',
                    imgUrl:'https://picbed.qunarzz.com/01d2f57f920666364197a850dab859a8.png',
                    desc:'民宿客栈'
                },
                {
                    id:'0002',
                    imgUrl:'https://picbed.qunarzz.com/83af731055e121a3251690b225327b56.png',
                    desc:'专车自驾'
                },
                {
                    id:'0003',
                    imgUrl:'https://picbed.qunarzz.com/1e107321f5396ea4994cd832232ecf8a.png',
                    desc:'旅游团购'
                },
                {
                    id:'0004',
                    imgUrl:'https://picbed.qunarzz.com/25e3b9f17a21a6e0113c57a23ffccde4.png',
                    desc:'周边短途'
                },
                {
                    id:'0005',
                    imgUrl:'https://picbed.qunarzz.com/01d2f57f920666364197a850dab859a8.png',
                    desc:'民宿客栈'
                },
                {
                    id:'0006',
                    imgUrl:'https://picbed.qunarzz.com/83af731055e121a3251690b225327b56.png',
                    desc:'专车自驾'
                },
                {
                    id:'0007',
                    imgUrl:'https://picbed.qunarzz.com/1e107321f5396ea4994cd832232ecf8a.png',
                    desc:'旅游团购'
                },
                {
                    id:'0008',
                    imgUrl:'https://picbed.qunarzz.com/25e3b9f17a21a6e0113c57a23ffccde4.png',
                    desc:'周边短途'
                },
                {
                    id:'0009',
                    imgUrl:'https://picbed.qunarzz.com/c65b3bb7571a6bd62df669213e44b84d.png',
                    desc:'一日游'
                },
            ]
        }
    },
    computed: {
        pages () {
            const pages= []
            this.iconsList.forEach((item,index) => {
                const page = Math.floor(index/8)
                if (!pages[page]) {
                    pages[page] = []
                }
                pages[page].push(item)
            })
            return pages;
        }
    }
}
</script>

<style lang="stylus" scoped>
    @import '~styles/varibles.styl'
    @import '~styles/mixins.styl'
      .icons >>> .swiper-container
        height: 0
        padding-bottom: 50%
      .icon
        position:relative
        overflow hidden
        float left
        width: 25%
        height: 0
        padding-bottom: 25%
        .icon-img
          position: absolute
          top: 0
          left: 0
          rigt: 0
          bottom: .44rem
          box-sizing border-box
          padding: .1rem
          .icon-img-content
            display:block
            margin:0 auto
            height:100%
        .icon-desc
          position absolute
          left: 0
          right: .2rem
          bottom: 0
          height: .44rem
          line-height: .44rem
          color :$darkTextColor
          text-align :center
          ellipsis()
</style>