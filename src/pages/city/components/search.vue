<template>
  <div class="search">
  	<input class="search-input" type="text" placeholder="输入城市名或拼音">
  </div>
</template>

<script>
export default {
  name: 'SearchHeader'
  
}
</script>

<style lang="stylus" scoped>
	@import '~styles/varibles.styl'
	.search
		height: .72rem
		background: $bgcolor
		padding: 0 .1rem
		.search-input
			box-sizing: border-box
			width: 100%
			height: .62rem
			line-height: .62rem
			color: #fff
			padding: 0 .1rem
			border-radius: .06rem
			text-align: center
			color: #666
</style>