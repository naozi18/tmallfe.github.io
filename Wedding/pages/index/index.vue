<template>
	<view class="content">
		<image class="bg" src="/static/bg_1.png" mode=""></image>
		<view class="bigBox">
			<view class="title">邀请函</view>
			<image class="box_img" src="../../static/avatar.png" mode=""></image>
			<view class="info">
				
					<!-- 左边新郎 -->
					<view class="">
						<view class="">王辉辉</view>
						<view class="">新郎</view>
						<image src="../../static/tel.png" mode=""></image>
					</view>
					
					<view class="">
						<image src="../../static/wedding.png" mode=""></image>
					</view>
					<view>
					<view class="">新娘</view>
					<view class="">王琳琳</view>
					<image src="../../static/tel.png" mode=""></image>
					</view>
				
			</view>
			
		</view>
		
		
		
		
	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style scoped lang="scss">
	page {
		height: 100%;
	}

	.content {
		width: 100%;
		height: 100%;
		position: relative;
		.bigBox {
			position: absolute;
			top: 420rpx;
			left: 50%;
			transform: translate(-50%, -50%);
			width: 630rpx;
			.info{
				display: flex;
				justify-content: space-around;
				align-items: center;
				
				image{
					width: 100rpx;
					height: 100rpx;
				}
			}

			.box_img {
				width: 300rpx;
				height: 300rpx;
				display: block;
				margin: 0 auto;
				border-radius: 50%;
				border: 3px solid $uni-color-theme;
			}

			.title {
				text-align: center;
				font-weight: 550;
				font-size: 60rpx;
				color: $uni-color-theme;
			}
		}

		.bg {
			position: absolute;
			z-index: -1;
			width: 100%;
			height: 100%;
		}
	}
</style>
