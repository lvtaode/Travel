<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page,index) of pages" :key="index">
        <div class="icon" v-for="item of page" :key="item.id">
          <div class="icon-img">
            <img class="icon-imgContent" :src="item.imgUrl" alt="">
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  props: {
    iconList: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        autoplay: false
      }
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang='stylus' scoped>
@import '~styles/varibles.styl'
@import '~styles/mixins.styl'
.icons >>>.swiper-container
  height: 0
  padding-bottom: 50%
.icons
  margin-top .1rem
  .icon
    overflow hidden
    position relative
    float left
    width 25%
    height 0
    padding-bottom 21.34%
    .icon-img
      position absoute
      top 0
      left 0
      right 0
      box-sizing border-box
      padding .1rem
      bottom .44rem
      .icon-imgContent
        display block
        margin 0 auto
        width 70%
    .icon-desc
      position absolute
      left 0
      right 0
      bottom 0
      height .35rem
      line-height .35rem
      text-align center
      color $darkTextColor
      ellipsis()
</style>
