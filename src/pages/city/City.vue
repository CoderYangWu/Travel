<template>
<div>
 <city-header></city-header>
 <city-search></city-search>
 <city-list></city-list>
 <city-alphabet></city-alphabet>
</div>
</template>

<script>
import CityAlphabet from './components/Alphabet.vue'
import CityHeader from './components/Header.vue'
import CityList from './components/List.vue'
import CitySearch from './components/Search.vue'

export default {
  components: { CityHeader, CitySearch, CityList, CityAlphabet },
    name: 'City'
}
</script>

<style lang="stylus" scoped>

</style>