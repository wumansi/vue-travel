<template>
  <div class="list" ref="wrapper">
  	<div>
	  	<div class="area">
	  		<div class="title bordertopbottom">当前城市</div>
	  		<div class="button-list">
	  			<div class="button-wrapper">
	  				<div class="button">北京</div>
	  			</div>
	  			<div class="button-wrapper">
	  				<div class="button">北京</div>
	  			</div>
	  			<div class="button-wrapper">
	  				<div class="button">北京</div>
	  			</div>
	  			<div class="button-wrapper">
	  				<div class="button">北京</div>
	  			</div>
	  		</div>
	  	</div>
	  	<div class="area">
	  		<div class="title bordertopbottom">热门城市</div>
	  		<div class="button-list">
	  			<div class="button-wrapper" v-for="item of hotCities" :key="item.id">
	  				<div class="button">{{item.name}}</div>
	  			</div>
	  		</div>
	  	</div>
	  	<div class="area" v-for="(item, key) of cities" :key="key" :ref="key">
	  		<div class="title bordertopbottom">{{key}}</div>
	  		<div class="item-list" v-for="val of item" :key="val.id">
	  			<div class="item border-bottom">{{val.name}}</div>
	  		</div>
	  	</div>
	  	
  	</div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'
export default {
  name: 'ListHeader',
  props: {
    cities: Object,
    hotCities: Array,
    letter: String
  },
  mounted () {
  	this.scroll = new BScroll(this.$refs.wrapper)
  },
  watch: {
    letter(){
      if(this.letter){
        const element = this.$refs[this.letter][0]
        this.scroll.scrollToElement(element)
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
	@import '~styles/varibles.styl'
	.bordertopbottom
		&:before
			border-color: #ccc
		&:after
			border-color: #ccc
	.border-bottom
		&:before
			border-color: #ccc
	.list
		overflow: hidden
		position: absolute
		top: 1.58rem
		left: 0
		right: 0
		bottom: 0
		.title
			line-height: .54rem
			background: #eee
			padding-left: .2rem
			color: #666
			font-size: .26rem
		.button-list
			padding: .1rem .6rem .1rem .1rem
			overflow: hidden
			.button-wrapper
				float: left
				width: 33.33%
				.button
					border: .02rem solid #ccc
					padding: .1rem 0
					text-align: center
					border-radius: .06rem
					margin: .1rem
		.item-list
			.item
				line-height: .76rem
				padding-left: .2rem
				color: #666
</style>