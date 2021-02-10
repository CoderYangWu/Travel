<template>
<div>
    <div class="title">周末去哪儿</div>
    <ul>
        <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
            <div class="item-img-wrapper">
            <img class="item-img" :src="item.imgUrl">   
            </div>
            <div class="item-info">
            <p class="item-title">{{item.title}}</p>
            <p class="item-desc">{{item.desc}}</p>
            </div>
        </li>
    </ul>
</div>
</template>

<script>
export default {
    name: "HomeWeekend",
    data () {
       return {
            recommendList: [
            {
            id:'0001',
            imgUrl:'https://imgs.qunarzz.com/sight/source/1505/98/47e8d7bdbed162.jpg_r_640x214_f6059302.jpg',
            title:'有温泉就任性',
            desc:'繁忙的一周结束，拖着疲惫的身体赶紧来泡个养生温泉吧，解除你的疲劳'
        },
            {
            id:'0002',
            imgUrl:'https://imgs.qunarzz.com/sight/source/1505/98/47e8d7bdbed162.jpg_r_640x214_f6059302.jpg',
            title:'有温泉就任性',
            desc:'繁忙的一周结束，拖着疲惫的身体赶紧来泡个养生温泉吧，解除你的疲劳'
        },
            {
            id:'0003',
            imgUrl:'https://imgs.qunarzz.com/sight/source/1505/98/47e8d7bdbed162.jpg_r_640x214_f6059302.jpg',
            title:'有温泉就任性',
            desc:'繁忙的一周结束，拖着疲惫的身体赶紧来泡个养生温泉吧，解除你的疲劳'
        },
        ]
       }
    }

}
</script>

<style lang="stylus" scoped>
    @import '~styles/mixins.styl'
    .title
      margin-top .2rem
      line-height .8rem
      background #eee
      text-indent .2rem
    .item-img-wrapper
      overflow hidden
      height 0
      padding-bottom 33.9%
    .item-img
      width 100%
    .item-info
      padding .1rem
      .item-title
        ellipsis()
        line-height .54rem
        font-size .32rem
      .item-desc
        line-height .4rem
        color #ccc
        ellipsis()
</style>