<template>
	<view class="back-arrow-left" :style="[posi]">
		<image class="img-32" src="../static/grey-arrow.png" mode=""></image>
	</view>
</template>

<script>
import { computed } from "vue"
	export default {
		data() {
			return {
				statusHeight: 0
			}
		}
	},
	onLoad() {
		const res = uni.getSystemInfoSync()
		this.statusHeight = res.statusBarHeight
	},
	computed: {
		posi() {
			return {
				top: this.statusHeight + 'px'
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
</style>