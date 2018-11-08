<template>
  <div>
      <city-header></city-header>
      <city-search></city-search>
      <city-list :hotCities="hotCities" :cities="cities"
                 :letter="letter">
      </city-list>
      <city-alphabet :cities="cities" @letter="letterClick"></city-alphabet>
  </div>
</template>

<script>
import axios from 'axios'
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/List'
import CityAlphabet from './components/Alphabet'
export default {
  name: 'City',
  components: {
    CityHeader,
    CitySearch,
    CityList,
    CityAlphabet
  },
  data () {
    return {
      cities: {},
      hotCities: [],
      letter: ''
    }
  },
  methods: {
    letterClick (msg) {
      this.letter = msg
    },
    getCityInfo () {
      axios.get('/api/city.json')
        .then(this.handleGetCityInfoSuccess)
    },
    handleGetCityInfoSuccess (res) {
      console.log(res)
      res = res.data
      if (res.ret && res.data) {
        this.cities = res.data.cities
        this.hotCities = res.data.hotCities
      }
    }
  },
  mounted () {
    this.getCityInfo()
  }
}
</script>

<style lang="stylus" scoped>

</style>
