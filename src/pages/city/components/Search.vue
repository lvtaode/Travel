<template>
  <div class="search">
    <input class="searchInput" type="text" placeholder="请输入城市名或拼音">
  </div>
</template>

<script>
export default {
  name: 'CitySearch'
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
  .search
    height .72rem
    padding 0 .1rem
    background-color $bgColor
    .searchInput
      width 100%
      height .62rem
      line-height .62rem
      text-align center
      padding 0 .1rem
      box-sizing border-box
      font-size .3rem
      color #666
      border-radius .06rem
</style>
