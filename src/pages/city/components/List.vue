<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">{{this.currentCity}}</div>
          </div>
        </div>
      </div>
     <div class="area">
      <div class="title border-topbottom">热门城市</div>
       <div class="button-list">
         <div
            class="button-wrapper"
            v-for="item of hot"
            :key="item.id"
            @click="handleCityClick(item.name)"
         >
           <div class="button">{{item.name}}</div>
         </div>
      </div>
     </div>
     <div
        class="area"
        v-for="(item,key) of cities"
        :key="key"
        :ref="key"
     >
        <div class="title border-topbottom">{{key}}</div>
        <ul class="item-list">
          <li
            class="item border-bottom"
            v-for="innerItem of item"
            :key="innerItem.id"
            @click="handleCityClick(innerItem.name)"
          >
              {{innerItem.name}}
          </li>
        </ul>
     </div>
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'
import {mapState, mapMutations} from 'vuex'
export default {
  name: 'CityList',
  props: {
    hot: Array,
    cities: Object,
    letter: String
  },
  computed: {
    ...mapState({
      currentCity: 'city'
    })
  },
  methods: {
    handleCityClick (city) {
      this.changeCity(city)
      this.$router.push('./')
    },
    ...mapMutations(['changeCity'])
  },
  mounted () {
    this.scroll = new BScroll(this.$refs.wrapper)
  },
  watch: {
    letter () {
      if (this.letter) {
        const elment = this.$refs[this.letter][0]
        this.scroll.scrollToElement(elment)
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
   @import '~styles/varibles.styl'
    .border-topbottom
      &:before
        border-color: #CCCCCC
      &:after
        border-color: #CCCCCC
    .border-bottom
      &:before
        border-color: #CCCCCC
    .list
      overflow: hidden
      position: absolute
      top:1.67rem
      left: 0
      right: 0
      bottom: 0
      .title
        line-height: 0.54rem
        padding-left: 0.2rem
        font-size: 0.26rem
        background: #EEEEEE
        color: #666666
      .button-list
        padding: 0.1rem 0.6rem 0.1rem 0.1rem
        overflow: hidden
        .button-wrapper
          float: left
          width: 33.33%
          .button
            margin: 0.1rem
            padding: 0.1rem 0
            text-align: center
            border: 0.01rem solid #CCCCCC
      .item-list
        .item
          line-height: 0.72rem
          padding-left: 0.2rem

</style>
