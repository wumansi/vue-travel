<template>
	<div>
		<city-header></city-header>
  		<search-header></search-header>
  		<list-header></list-header>
  		<city-alphabet></city-alphabet>
	</div>
</template>

<script>
import CityHeader from './components/header.vue'
import SearchHeader from './components/search.vue'
import ListHeader from './components/list.vue'
import CityAlphabet from './components/alphabet.vue'

export default {
  name: 'City',
  components: {
  	CityHeader,
  	SearchHeader,
  	ListHeader,
  	CityAlphabet
  }
}
</script>

<style lang="stylus" scoped>

</style>