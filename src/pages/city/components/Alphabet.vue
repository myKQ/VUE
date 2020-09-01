<template>
  <ul class="list">
    <li class="item" 
      v-for="item of letters" 
      :key="item"
      :ref="item"
      @touchstart="handleTouchStart"
      @touchmove="handleTouchMove"
      @touchend="handleTouchEnd"
      @click="cityClick"
    >
      {{item}}
    </li>
  </ul>
</template>

<script>
export default {
  name: 'CityAlphabet',
  props: {
    cities:Object
  },
  data () {
    return {
      touchStatus: false
    }
  },
  computed: {
  // 将所有字母从cities对象取出存入数组
  letters () {
    const letters = []
      for (let i in this.cities) {
        letters.push(i)
      }
      return letters
    }
  },
  methods: {
    cityClick (e) {
      this.$emit('change',e.target.innerText)
    },
    handleTouchStart () {
      this.touchStatus = true
    },
    handleTouchMove (e) {
      if (this.touchStatus) {
          // A字母距离搜索框底部的距离
          const startY = this.$refs['A'][0].offsetTop
          // 触发点距离搜索框底部的距离 = 触发点距离顶部的距离-头部高度（79）
          const touchY = e.touches[0].clientY - 79
          // 相减后就是触发点距离A的距离/每个字母的高度（20）index就是第几个字母
          const index = Math.floor((touchY - startY) / 20)
          if (index >= 0 && index < this.letters.length) {
            this.$emit('change', this.letters[index])
          }
      }
    },
    handleTouchEnd () {
      this.touchStatus = false
    }
  }
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
      text-align: center
      color: $bgColor
</style>
