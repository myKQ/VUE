<template>
  <div>
    <div class="title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom" v-for="item of list" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl" />
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  data () {
    return {
      list:[{
          id:'001',
          imgUrl:'https://imgs.qunarzz.com/p/p90/201212/11/0478fce0303c5f3093835fbb.jpg_150x100_fa534adf.jpg',
          title:'大连旅行，交通、酒店、景点一站式服务',
          desc:'行程、奢简可调'
        },{
          id:'002',
          imgUrl:'https://imgs.qunarzz.com/p/p79/201302/28/aed3769b586e4c6d93835fbb.jpg_150x100_6df8c9bc.jpg',
          title:'大连旅行，交通、酒店、景点一站式服务',
          desc:'行程、奢简可调'
        },{
          id:'003',
          imgUrl:'https://imgs.qunarzz.com/p/p90/1809/e1/ae215d58a27fd202.jpg_750x500_a28a452a.jpg',
          title:'大连旅行，交通、酒店、景点一站式服务',
          desc:'行程、奢简可调'
        }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .title
    line-height: .8rem
    background: #eee
    text-indent: .2rem
  .item-img-wrapper
    overflow: hidden
    height: 0
    padding-bottom: 37.09%
    .item-img
      width: 100%
  .item-info
    padding: .1rem
    .item-title
      line-height: .54rem
      font-size: .32rem
      ellipsis()
    .item-desc
      line-height: .4rem
      color: #ccc
      ellipsis()
</style>
