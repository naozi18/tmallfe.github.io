<template>
	<view class="content">
		<swiper autoplay="autoplay":indicator-dost="indicator":indicator-color="color":indicator-active-color="selectColor":interval="2000">
			<swiper-item>
				<image src="../../static/timg1.jpg"></image>
			</swiper-item>
			<swiper-item>
				<image src="../../static/timg2.jpg"></image>
			</swiper-item>
			<swiper-item>
				<image src="../../static/timg3.jpg"></image>
			</swiper-item>
			<swiper-item>
				<image src="../../static/timg4.jpg"></image>
			</swiper-item>
		</swiper>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				autoplay:true,
				indicator:true,
				vertical:true,
				color:"white",
				selectColor:"red",
				
				
			}
		},
		methods: {
			
		}
	}
</script>

<style scoped lang="scss">
	page{
		height: 100%;
	}
	.content{
		height: 100%;
		swiper{
			height: 100%;
			image{
				width: 100vmin;
				height: 100vh;
			}
		}
	}
</style>
