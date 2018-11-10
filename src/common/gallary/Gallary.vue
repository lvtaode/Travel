<template>
  <div class="container" @click="handleGallaryClick">
    <div calss=wrapper>
      <swiper :options="swiperOption">
      <!-- slides -->
        <swiper-slide v-for="(item, index) of imgs" :key="index">
          <img class="gallary-img" :src="item" alt="">
        </swiper-slide>
        <!-- Optional controls -->
        <div class="swiper-pagination"  slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CommonGallary',
  props: {
    imgs: {
      type: Array,
      default () {
        return []
      }
    }
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        observer: true,
        observeParents: true
      }
    }
  },
  methods: {
    handleGallaryClick () {
      this.$emit('close')
    }
  }
}
</script>

<style lang="stylus" scoped>
.container
  display flex
  flex-direction column
  justify-content center
  position fixed
  z-index 99
  left 0
  right 0
  top 0
  bottom 0
  background #000
  .wrapper
    width 100%
    height 0
    padding-bottom 100%
.container >>> .gallary-img
  width 100%
.container >>> .swiper-pagination
  bottom -2rem
  color #fff
.container >>> .swiper-container
  overflow inherit
</style>
