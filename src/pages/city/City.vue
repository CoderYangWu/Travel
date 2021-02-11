<template>
<div>
 <city-header></city-header>
 <city-search :cities="cities"></city-search>
 <city-list :cities="cities" :hot="hotCities" :letter="letter"></city-list>
 <city-alphabet :cities="cities"
                @change="handleLetterChange"></city-alphabet>
</div>
</template>

<script>
import Axios from 'axios'
import CityAlphabet from './components/Alphabet.vue'
import CityHeader from './components/Header.vue'
import CityList from './components/List.vue'
import CitySearch from './components/Search.vue'
import axios from 'axios'
export default {
  components: { CityHeader, CitySearch, CityList, CityAlphabet },
    name: 'City',
    data() {
      return{
        cities: {},
        hotCities:[],
        letter:''
      }
    },
    methods: {
      getCityInfo () {
        axios.get('/api/city.json')
          .then(this.handleGetCityInfoSucc)
      },
      handleGetCityInfoSucc(res) {
        res=res.data
        if(res.ret && res.data) {
          const data = res.data
          this.cities=data.cities
          this.hotCities=data.hotCities
        }

      },
      handleLetterChange(letter) {
        this.letter=letter
      }
    },
    mounted () {
      this.getCityInfo ();
    }
}
</script>

<style lang="stylus" scoped>

</style>