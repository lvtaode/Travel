<template>
  <div>
    <detail-banner :sightName="sightName"
                   :bannerImg="bannerImg"
                   :gallaryImgs="gallaryImgs">
    </detail-banner>
    <detail-header></detail-header>
    <div class="content">
      <detail-list :list="list"></detail-list>
    </div>
  </div>
</template>

<script>
import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
import DetailList from './components/List'
import axios from 'axios'
export default {
  name: 'Detail',
  components: {
    DetailBanner,
    DetailHeader,
    DetailList
  },
  data () {
    return {
      list: [],
      sightName: '',
      gallaryImgs: [],
      bannerImg: ''
    }
  },
  mounted () {
    this.getDetailInfo()
  },
  methods: {
    getDetailInfo () {
      console.log(this.$route.params.id)
      axios.get('api/detail.json', {
        params: {
          id: this.$route.params.id
        }
      }).then(this.handleGetDataSucc)
    },
    handleGetDataSucc (res) {
      res = res.data
      console.log(res)
      if (res.ret && res.data) {
        this.sightName = res.data.sightName
        this.bannerImg = res.data.bannerImg
        this.gallaryImgs = res.data.gallaryImgs
        this.list = res.data.categoryList
      }
    }
  }
}
</script>

<style lang='stylus' scoped>
.content
  height 20rem
</style>
