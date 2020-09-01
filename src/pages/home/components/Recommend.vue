<template>
	<div>
		<div class="title">热门推销</div>
		<ul>
			<li class="item border-bottom" v-for="item of recommendList" :key="item.id">
				<img class="item-img" :src="item.imgUrl">
				<div class="item-info">
					<p class="item-title">{{item.title}}</p>
					<p class="item-desc">{{item.desc}}</p>
					<button class="item-button">查看详情</button>
				</div>
			</li>
		</ul>
	</div>
</template>
<script>
	export default {
		name:'HomeRecommend',
		data () {
			return {
				recommendList:[{
					id:'001',
					imgUrl:'https://imgs.qunarzz.com/p/p90/1809/e1/ae215d58a27fd202.jpg_750x500_a28a452a.jpg',
					title:'大连旅行，交通、酒店、景点一站式服务',
					desc:'行程、奢简可调'
				},{
					id:'002',
					imgUrl:'https://imgs.qunarzz.com/p/p90/1809/e1/ae215d58a27fd202.jpg_750x500_a28a452a.jpg',
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
		margin-top: .2rem
		line-height: .8rem
		background: #eee
		text-indent: .2rem
	.item
		overflow: hidden
		display: flex
		height: 1.9rem
		.item-img
			width: 1.7rem
			height: 1.7rem
			padding: .1rem
		.item-info
			flex: 1
			padding: .1rem
			min-width: 0
			.item-title
				line-height: .54rem
				font-size: .32rem
				ellipsis()
			.item-desc
				line-height: .4rem
				color: #ccc
				ellipsis()
			.item-button
				line-height: .44rem
				margin-top: .16rem
				background: #ff9300
				padding: 0 .2rem
				border-radius: .06rem
				color: #fff
</style>