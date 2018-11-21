<template>
    <ul class="list">
		<div class="item border-bottom">A</div>
		<div class="item border-bottom">A</div>
		<div class="item border-bottom">A</div>
		<div class="item border-bottom">A</div>
		<div class="item border-bottom">A</div>
	</ul>
</template>

<script>
export default {
  name: 'CityAlphabet',
  
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.list
	display: flex
	flex-direction: column
	justify-content: center
	position: absolute
	top: 1.58rem
	right: 0
	bottom: 0
	width: .4rem
	.item
		line-height: .4rem
		padding-left: .2rem
		color: $bgcolor
</style>
