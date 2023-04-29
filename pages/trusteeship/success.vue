<template>
	<view class="">
		<view class="img-box flex align-center justify-center">
			<image class="img-200" src="../../static/green-success.png" mode="aspectFit"></image>
		</view>
		<view class="flex align-center justify-center c-333 u-font-32 u-m-b-30">
			申请成功
		</view>
		<view class="flex align-center justify-center c-999 u-font-28 u-m-b-30">
			我们将会在1-3个工作日内联系您，
			请保持电话畅通
		</view>
		<view class="u-p-t-30 flex align-center justify-center">
			<view class="back-btn flex align-center justify-center" @tap="handleToHome">
				返回首页
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
		methods: {
			handleToHome() {
				uni.switchTab({
					url:'/pages/house/index'
				})
			}
		}
	}
</script>

<style lang="scss" scoped>
	.img-box {
		padding-top: 180rpx;
		margin-bottom: 40rpx;
	}

	.img-200 {
		width: 200rpx;
		height: 200rpx;
	}

	.back-btn {
		font-size: 32rpx;
		color: #B2B2B2;
		font-weight: 500;
		width: 278rpx;
		height: 90rpx;
		border: 2rpx solid #B2B2B2;
	}
</style>
