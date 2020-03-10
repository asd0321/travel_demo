<template>
	<div class="wrapper">
		<swiper :options="swiperOption" v-if="showSwiper">
	    <!-- slides -->
		    <swiper-slide v-for="item of list" :key="item.id">
		    	<img class="swiper-img" :src="item.imgUrl" alt="">
		    </swiper-slide>
		    <!-- Optional controls -->
		    <div class="swiper-pagination"  slot="pagination"></div>
		</swiper>
	</div>
</template>

<script>
	export default{
		name:'HomeSwiper',
		props:{
			list:Array
		},
		data(){
			return{
				swiperOption:{
					pagination:'.swiper-pagination',
					loop:true
				}
			}
		},
		computed:{
			showSwiper(){
				return this.list.length
			}
		}

	}
</script>

<style lang="stylus" scoped>
	.wrapper>>>.swiper-pagination-bullet-active
		background:#fff !important
		margin-bottom:2.3rem
	.wrapper
		overflow:hidden
		// height:31.25vw
		width:100%
		height:0
		padding-bottom:31.25%
		background:#eee
		.swiper-img
			width:100%
</style>