<template>
  <div>
    <router-link to="/"
                 tag="div"
                 class="header-abs"
                 v-show="showAbs">
        <div class="iconfont back-icon">&#xe624;</div>
    </router-link>
    <div class="header-fixed" v-show="!showAbs" :style="opacityStyle">
      景点详情
      <router-link to='/'>
        <div class="iconfont header-back">&#xe624;</div>
      </router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showAbs: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleScroll)
  },
  methods: {
    handleScroll () {
      // console.log(document.documentElement.scrollTop)
      const top = document.documentElement.scrollTop || window.pageYOffset || document.body.scrollTop
      if (top > 50) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = {
          opacity
        }
        this.showAbs = false
      } else {
        this.showAbs = true
      }
    }
  }
}
</script>

<style lang='stylus' scoped>
@import '~styles/varibles.styl'
.header-abs
  position absolute
  left .2rem
  top .2rem
  width .8rem
  height .8rem
  line-height .8rem
  text-align: center
  border-radius .4rem
  background rgba(0, 0, 0, .8)
  .back-icon
    font-size: .4rem
    font-weight: 600
    color #fff
.header-fixed
  position fixed
  z-index 2
  top 0
  right 0
  left 0
  height $headerHeight
  line-height $headerHeight
  background $bgColor
  text-align center
  color #fff
  font-size .32rem
  .header-back
    position absolute
    top 0
    left 0
    width .64rem
    font-size .4rem
    text-align center
    color #fff
    font-weight 600
</style>
