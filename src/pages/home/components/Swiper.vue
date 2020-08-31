<template>
	<div class="swiper">
		<swiper :options="swiperOptions">
		    <swiper-slide v-for="item of swiperList" :key="item.id">
		    	<img class="swiper-img" :src="item.imgUrl">
		    </swiper-slide>
		    <div class="swiper-pagination" slot="pagination"></div>
		</swiper>
	</div>
</template>
<script>
export default {
	name:'HomeSwiper',
	data () {
		return {
			swiperOptions:{
				pagination: '.swiper-pagination',
				loop:true
			},
			swiperList:[{
				id:'001',
				imgUrl:'//imgs.qunarzz.com/vs_ceph_vcimg/b8c4527c41649814cc4cf86880abba54.jpeg'
			},{
				id:'002',
				imgUrl:'//imgs.qunarzz.com/vc/e3/a1/71/f498dfd3bed948d623c9093252.jpg_92.jpg'
			}]
		}
	}
}
</script>
<style lang="stylus" scoped>
	.swiper >>> .swiper-pagination-bullet-active
		background-color:#fff
	.swiper
		width:100%
		overflow:hidden
		height:0
		padding-bottom:31.25%
		.swiper-img
			width:100%
			background-color:#ccc
		
</style>