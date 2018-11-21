<template>
	<div>
		<city-header></city-header>
  		<search-header></search-header>
  		<list-header :cities="cities" :hotCities="hotCities"></list-header>
  		<city-alphabet :cities="cities"></city-alphabet>
	</div>
</template>

<script>
import CityHeader from './components/header.vue'
import SearchHeader from './components/search.vue'
import ListHeader from './components/list.vue'
import CityAlphabet from './components/alphabet.vue'
import axios from 'axios'
export default {
  name: 'City',
  components: {
  	CityHeader,
  	SearchHeader,
  	ListHeader,
  	CityAlphabet
  },
  data (){
  	return{
      cities: {},
  	  hotCities: []
  	}
  },
  methods: {
  	getCityInfo(){
  		axios.get('/api/city.json')
  		.then(this.getCitySucc)
  	},
  	getCitySucc(res){
  		console.log(res)
      res = res.data
      if(res.ret && res.data){
        const data = res.data;
        this.cities = data.cities;
        this.hotCities = data.hotCities
      }
  	}
  },
  mounted (){
  	this.getCityInfo()
  }
}
</script>

<style lang="stylus" scoped>

</style>