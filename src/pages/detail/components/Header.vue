<template>
  <div>
    <router-link tag="div" to="/" class="header-abs" v-show="showAbs">
        <div class="iconfont header-abs-back">&#xe658;</div>
    </router-link>
    <div class="header-fixed" v-show="!showAbs" :style="opacityStyle">
        <router-link to="/">
            <div class="iconfont header-fixed-back">&#xe658;</div>
        </router-link>
        景点详情
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showAbs: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop || document.body.scrollTop || window.pageYOffset
      if (top > 60) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = {
          opacity
        }
        this.showAbs = false
      } else {
        this.showAbs = true
      }
    }
  },
  mounted () {
    window.addEventListener('scroll', this.handleScroll)
  },
  destroyed () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/variables.styl'
  .header-abs
    position: absolute
    left: .2rem
    top: .2rem
    width: .6rem
    height: .6rem
    border-radius: .4rem
    background: rgba(0, 0, 0, .8)
    line-height: .6rem
    .header-abs-back
      color: #ffffff
      font-size: .5rem
      text-align: center
  .header-fixed
    z-index: 2
    height: $headerHeight
    line-height: $headerHeight
    text-align: center
    color: #ffffff
    background $bgColor
    font-size: .32rem
    position: fixed
    top: 0
    left: 0
    right: 0
    .header-fixed-back
      width: .64rem
      font-size: .64rem
      text-align: center
      position: absolute
      top: 0
      left: 0
      color: #fff
</style>
