<template>
  <div>
    <div class="recommend-title">热销推荐</div>
    <ul>
      <li class="item">
        <img class="item-img" src="http://img1.qunarzz.com/sight/p0/1602/de/de8400021b664c5390.img.jpg_200x200_46b16057.jpg" alt="">
        <div class="item-info">
          <p class="item-title">的设等数据库计费</p>
          <p class="item-desc">大会上尽快发货时的授课方式可发货速度快黑客技术</p>
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
  .recommend-title
    line-height .8rem
    background-color #eee
    text-indent .2rem
    .item
      overflow hidden
      display flex
      height 1.9rem
      background red
    .item-img
      width 1rem
      height 1rem
      padding .1rem
</style>
