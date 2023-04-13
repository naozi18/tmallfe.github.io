<template>
	<view>
		1111
		<picker class="picker":range="array" >
			<view class="uni-input"></view>
		</picker>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				array: [1, 2, 3, 4, 5]
			}
		},
		methods: {

		}
	}
</script>

<style>
	.picker {
		height: 100rpx;
		background-color: red;
	}
</style>
