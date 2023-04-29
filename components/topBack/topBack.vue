<template>
	<view class="back-arrow-left" :style="{top: statusHeight+'px'}" @tap="handleBack">
		<view class="arrow-square">
			
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				statusHeight: 0
			}
		},
		created() {
			const res = uni.getSystemInfoSync()
			console.log(res,'rea')
			this.statusHeight = res.statusBarHeight + 10
		},
		computed: {

		},
		methods: {
			handleBack() {
				uni.navigateBack()
			}
		}
	}
</script>

<style lang="scss" scoped>
	.back-arrow-left {
		position: fixed;
		left: 34rpx;
		z-index: 10086;
	}
	.arrow-square {
		width: 24rpx;
		height: 24rpx;
		border: 1px solid #fff;
		border-left: none;
		border-bottom: none;
		transform: rotate(-135deg);
	}
</style>