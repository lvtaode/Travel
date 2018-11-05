<template>
  <div>
    <div class="recommend-title">热销推荐</div>
    <ul>
      <li class="item border-bottom">
        <img class="item-img" src="http://img1.qunarzz.com/sight/p0/1602/de/de8400021b664c5390.img.jpg_200x200_46b16057.jpg" alt="">
        <div class="item-info">
          <p class="item-title">的设等数据库计费</p>
          <p class="item-desc">大会上尽快dfdgg发货时发货速度快黑客技术</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend'
}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
  .recommend-title
    line-height .8rem
    background-color #eee
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
      display-flex 1
      padding .1rem
      min-width 0
      .item-title
        line-height .54rem
        font-size .32rem
        ellipsis()
      .item-desc
        line-height .4rem
        color #ccc
        ellipsis()
      .item-button
        line-height .44rem
        margin-top .2rem
        background #ff9300
        padding 0 .2rem
        border-radius .06rem
        color #fff
</style>
