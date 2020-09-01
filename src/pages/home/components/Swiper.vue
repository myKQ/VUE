<template>
	<div class="swiper">
		<swiper :options="swiperOptions" v-if="showSwiper">
		    <swiper-slide v-for="item of list" :key="item.id">
		    	<img class="swiper-img" :src="item.imgUrl">
		    </swiper-slide>
		    <div class="swiper-pagination" slot="pagination"></div>
		</swiper>
	</div>
</template>
<script>
export default {
	name:'HomeSwiper',
	props:{
		list:Array
	},
	data () {
		return {
			swiperOptions:{
				pagination: '.swiper-pagination',
				loop:true
			}
		}
	},
	computed:{ 
		showSwiper () {
			return this.list.length
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
		padding-bottom:30.25%
		.swiper-img
			width:100%
			background-color:#ccc
		
</style>