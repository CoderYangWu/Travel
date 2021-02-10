<template>
<div>
    <div class="recommend-title">热销推荐</div>
    <ul>
        <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
            <img class="item-img" :src="item.imgUrl">
            <div class="item-info">
            <p class="item-title">{{item.title}}</p>
            <p class="item-desc">{{item.desc}}</p>
            <button class="item-button">查看详情</button>
            </div>
        </li>
    </ul>
</div>
</template>

<script>
export default {
    name: "HomeRecommend",
    data () {
       return {
            recommendList: [
            {
            id:'0001',
            imgUrl:'https://imgs.qunarzz.com/sight/p0/1505/bf/bf0ddc1cc474e026.water.jpg_250x250_d208ab43.jpg',
            title:'大连铭湖滑雪场',
            desc:'很好，一家人都去了，玩的很开心'
        },
            {
            id:'0002',
            imgUrl:'https://imgs.qunarzz.com/sight/p0/1505/bf/bf0ddc1cc474e026.water.jpg_250x250_d208ab43.jpg',
            title:'大连铭湖滑雪场',
            desc:'很好，一家人都去了，玩的很开心'
        },
            {
            id:'0003',
            imgUrl:'https://imgs.qunarzz.com/sight/p0/1505/bf/bf0ddc1cc474e026.water.jpg_250x250_d208ab43.jpg',
            title:'大连铭湖滑雪场',
            desc:'很好，一家人都去了，玩的很开心'
        },
        ]
       }
    }

}
</script>

<style lang="stylus" scoped>
    @import '~styles/mixins.styl'
    .recommend-title
      margin-top .2rem
      line-height .8rem
      background #eee
      text-indent .2rem
    .item
      overflow hidden
      display flex
      height 1.9rem
      .item-img
        width 1.7rem
        height 1.7rem
        padding .1rem
      .item-info
        flex 1
        padding .1rem
        min-width 0
        .item-title
          ellipsis()
          line-height .54rem
          font-size .32rem
        .item-desc
          line-height .4rem
          color #ccc
          ellipsis()
        .item-button
          margin-top .16rem
          line-height .44rem
          background #ff9300
          color #fff
          padding 0 .1rem
          border-radius .06rem
</style>