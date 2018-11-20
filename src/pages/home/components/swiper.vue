<template>
  <div class="wrapper">
	<swiper :options="swiperOption">
    	<!-- slides -->
	    <swiper-slide v-for="item of swiperList" :key="item.id">
	    	<img class="swiper-img" :src="item.url">
	    </swiper-slide>
	    <!-- Optional controls -->
	    <div class="swiper-pagination"  slot="pagination"></div>
	   
	 </swiper>
  </div>
  
</template>
<script>

  export default {
    name: 'HomeSwiper',
   	data () {
   		return{
   			swiperOption: {
   				pagination: '.swiper-pagination',
   				loop: true
   			},
   			swiperList: [{
				id:'001',
				url: 'http://img1.qunarzz.com/piao/fusion/1801/1a/94428c6dea109402.jpg_640x200_2cf590d8.jpg'   			
			},{
				id:'002',
				url: 'http://img1.qunarzz.com/piao/fusion/1802/42/7c92b9a381e46402.jpg_640x200_1cdce2a4.jpg'
			},{
				id:'003',
				url: 'http://img1.qunarzz.com/piao/fusion/1802/51/e78f936a5b404102.jpg_640x200_c14f0b3a.jpg'
			},{
				id:'004',
				url: 'http://img1.qunarzz.com/piao/fusion/1712/91/a275569091681d02.jpg_640x200_0519ccb9.jpg'
			}]
   		}
   	}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="stylus" scoped>
.wrapper >>> .swiper-pagination-bullet-active
	background: #fff
.wrapper
	width: 100%
	height: 0
	overflow: hidden
	padding-bottom: 31.25%
	background: #eee
	.swiper-img
		width: 100%
</style>
