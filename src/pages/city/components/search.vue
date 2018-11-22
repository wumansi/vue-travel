<template>
  <div>
    <div class="search">
    	<input v-model="keyword" class="search-input" type="text" placeholder="输入城市名或拼音">
    </div>
    <div class="search-content" ref="search" v-show="keyword">
      <ul>
        <li class="search-item border-bottom" v-for="item of list" :key="item.id">
         {{item.name}}
        </li>
        <li class="search-item border-bottom" v-show="hasList">找不到匹配项</li>
      </ul>
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'
export default {
  name: 'SearchHeader',
  props: {
    cities: Object
  },
  data(){
    return{
      list: [],
      keyword: ""
    }
  },
  computed: {
    hasList(){
      return !this.list.length
    }
  },
  watch:{
    keyword(){
      const result = []
      if(!this.keyword){
        this.list = []
        return
      }
      for(let i in this.cities){
        this.cities[i].forEach((value) => {
          if(value.spell.indexOf(this.keyword) > -1
            || value.name.indexOf(this.keyword) > -1){
            result.push(value)
          }
        })
      }
      this.list = result
    }
  },
  mounted () {
    this.scroll = new BScroll(this.$refs.search)
  }
}
</script>

<style lang="stylus" scoped>
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
.search-content
  position: absolute
  top: 1.58rem
  left: 0
  right: 0
  bottom: 0
  z-index: 1
  overflow: hidden   
  background: #eee
  .search-item
    line-height: .62rem
    padding-left: .2rem
    background: #fff
    color: #666
</style>