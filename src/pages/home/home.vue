<template>
  <div>
    <home-header :city="city"></home-header>
    <home-swiper :list="swiperList"></home-swiper>
    <home-icons :list="iconList"></home-icons>
    <home-recommend :list="recommendList"></home-recommend>
    <weekend :list="weekendList"></weekend>
  </div>
</template>

<script>
  import HomeHeader from './components/header'
  import HomeSwiper from './components/swiper'
  import HomeIcons from './components/icons'
  import HomeRecommend from './components/recommend'
  import Weekend from './components/weekend'
  import axios from 'axios'
  export default {
    name: 'Home',
    data () {
      return{
        city: "",
        swiperList: [],
        iconList: [],
        recommendList: [],
        weekendList: []
      }
    },
    components: {
      HomeHeader,
      HomeSwiper,
      HomeIcons,
      HomeRecommend,
      Weekend
    },
    methods: {
      getHomeInfo (){
        axios.get('/api/index.json')
        .then(this.getHomeInfoSucc)
      },
      getHomeInfoSucc (res) {
        console.log(res)
        res = res.data
        if(res.ret && res.data){
          var data = res.data
          this.city = res.city
          this.swiperList = data.swiperList
          this.iconList = data.iconList
          this.recommendList = data.recommendList
          this.weekendList = data.weekendList
        }
      }
    },
    mounted () {
      this.getHomeInfo()
    }
}
</script>

<style scoped>

</style>
