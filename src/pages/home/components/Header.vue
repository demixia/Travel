<template>
    <div class="header">
        <div class="header-left">
          <div class="iconfont back-icon">&#xe658;</div>
        </div>
        <div class="header-input"><span class="iconfont">&#xe63c;</span>输入城市/景点</div>
        <router-link to="/city">
          <div class="header-right arrow-icon">{{this.city}}<span class="iconfont">&#xe65c;</span></div>
        </router-link>
    </div>
</template>

<script>
import {mapState, mapGetters} from 'vuex'
export default {
  name: 'HomeHeader',
  computed: {
    ...mapState(['city']),
    ...mapGetters(['doubleCity'])
  }
}
</script>

<style lang="stylus" scoped>
    @import '~styles/variables.styl'
    .header
      display: flex
      line-height: $headerHeight
      background: $bgColor
      color: #fff
      .header-left
        width: .64rem
        float: left
        .back-icon
          text-align: center
          font-size: 0.4rem
      .header-input
        flex: 1
        height: .64rem
        margin-top: 0.12rem
        margin-left: .2rem
        padding-left: .2rem
        background: #fff
        border-radius: .1rem
        color: #cccccc
        line-height: .64rem
      .header-right
        min-width: 1.04rem
        padding: 0 .1rem
        float: right
        text-align: center
        color: #fff
        .arrow-icon
          margin-left: -0.04rem
          font-size: 0.24rem
</style>
