<template>
	<div class="icons">
		<swiper :options="swiperOption">
			<swiper-slide v-for="(page,index) of pages" :key="index">
				<div class="icon" v-for="item of page" :key="item.id">
					<div class="icon-img">
						<img :src="item.imgUrl">
					</div>
					<p class="icon-text">{{item.desc}}</p>
				</div>
		    </swiper-slide>
		</swiper>
	</div>
</template>

<script>
	export default {
		name:'Icons',
		data () {
			return {
				swiperOption: {
			        autoplay: false
			    },
				iconList:[
					{
						id:'001',
						imgUrl:'//s.qunarzz.com/homenode/images/touchheader/hotel.png',
						desc:'热门景点2144444444444444'
					},{
						id:'002',
						imgUrl:'//s.qunarzz.com/homenode/images/touchheader/hotel.png',
						desc:'热门景点'
					},{
						id:'003',
						imgUrl:'//s.qunarzz.com/homenode/images/touchheader/hotel.png',
						desc:'热门景点'
					},{
						id:'004',
						imgUrl:'//s.qunarzz.com/homenode/images/touchheader/hotel.png',
						desc:'热门景点'
					},{
						id:'005',
						imgUrl:'//s.qunarzz.com/homenode/images/touchheader/hotel.png',
						desc:'热门景点'
					},{
						id:'006',
						imgUrl:'//s.qunarzz.com/homenode/images/touchheader/hotel.png',
						desc:'热门景点'
					},{
						id:'007',
						imgUrl:'//s.qunarzz.com/homenode/images/touchheader/hotel.png',
						desc:'热门景点'
					},{
						id:'008',
						imgUrl:'//s.qunarzz.com/homenode/images/touchheader/hotel.png',
						desc:'热门景点'
					},{
						id:'009',
						imgUrl:'//s.qunarzz.com/homenode/images/touchheader/hotel.png',
						desc:'热门景点'
					}
				]
			}
		},
		computed:{
			pages () {
				const pages = []
				this.iconList.forEach((item,index) => {
					console.log(item,index)
					const page = Math.floor(index/8)
					if (!pages[page]) {
			          pages[page] = []
			        }
					pages[page].push(item)
				})
				return pages
			}
		}
	}
</script>
<style lang='stylus' scoped>
	@import '~styles/varibles.styl'
	@import '~styles/mixins.styl'
	.icons
		overflow:hidden
		height:0
		padding-bottom:50%
		.icon
			position:relative
			overflow:hidden
			width:25%
			height:0
			padding-bottom:25%
			float:left
			.icon-img
				position:absolute
				top:0
				left:0
				right:0
				bottom:.44rem
				padding:.1rem
				box-sizing:border-box	
				position: absolute
				img
					display: block
					margin: 0 auto
					height: 100%
			.icon-text
				position:absolute
				left:0
				right:0
				bottom:0
				height:.44rem
				line-height: .44rem
				text-align: center
				color:$darkTextColor
				ellipsis()
				// display:flex
				// justify-center:center
					
</style>