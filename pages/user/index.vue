<template>
	<view class="">
		<image class="img-562" src="../../static/personal-bg.png" mode=""></image>
		<view class="" :style="{height: statusHeight + 'px'}">
			
		</view>
		<view class="user-info-box flex align-center">
			<u-avatar :src="src"></u-avatar>
			<view class="u-m-l-20 u-font-26 c-white">
				<view class="w-600 u-m-b-10">
					贺若萌
				</view>
				<view class="">
					13812345678
				</view>
			</view>
		</view>
		<view class="info-box u-m-b-20 u-p-30 bg-white">
			<view class="flex align-center u-m-b-30" @tap="handleTo">
				<view class="info-line">
					
				</view>
				<text class="c-black w-600 flex-1 u-font-30">打扫金额统计</text>
				<text style="color: #989898;" class="u-font-24">打扫历史</text>
				<image class="img-28 u-m-l-6" src="../../static/grey-arrow.png" mode=""></image>
			</view>
			<view class="flex">
				<view class="flex-1">
					<view class="u-m-b-10 u-font-24" style="color: #989898;">
						今日金额
					</view>
					<view class="c-333 u-font-30">
						100.00
					</view>
				</view>
				<view class="flex-1">
					<view class="u-m-b-10 u-font-24" style="color: #989898;">
						本月金额
					</view>
					<view class="c-333 u-font-30">
						100.00
					</view>
				</view>
				<view class="flex-1">
					<view class="u-m-b-10 u-font-24" style="color: #989898;">
						累计金额
					</view>
					<view class="c-333 u-font-30">
						100.00
					</view>
				</view>
			</view>
		</view>
		
		<view class="info-box u-m-b-20 u-p-30 bg-white">
			<view class="flex align-center u-m-b-30">
				<view class="info-line">
					
				</view>
				<text class="c-black w-600 flex-1 u-font-30">打扫数量统计</text>
			</view>
			<view class="flex">
				<view class="flex-1">
					<view class="u-m-b-10 u-font-24" style="color: #989898;">
						今日已打扫
					</view>
					<view class="c-333 u-font-30">
						2
					</view>
				</view>
				<view class="flex-1">
					<view class="u-m-b-10 u-font-24" style="color: #989898;">
						本月已打扫
					</view>
					<view class="c-333 u-font-30">
						2
					</view>
				</view>
				<view class="flex-1">
					<view class="u-m-b-10 u-font-24" style="color: #989898;">
						累计已打扫
					</view>
					<view class="c-333 u-font-30">
						2
					</view>
				</view>
			</view>
		</view>
		<view class="logout-btn flex align-center justify-center">
			<text class="u-font-32 c-white w-600">退出登录</text>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				statusHeight: 44,
				src: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fc-ssl.duitang.com%2Fuploads%2Fblog%2F202106%2F09%2F20210609081952_51ef5.thumb.1000_0.jpg&refer=http%3A%2F%2Fc-ssl.duitang.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1681223586&t=8b75b0932ad4e8775c06eab09fe8af53',
			}
		},
		onLoad() {
			const res = uni.getSystemInfoSync()
			this.statusHeight = this.statusHeight + res.statusBarHeight
		},
		methods: {
			handleTo() {
				uni.navigateTo({
					url:'/pages/user/ecoLogList'
				})
			}
		}
	}
</script>

<style lang="scss" scoped>
	.img-562 {
		width: 100vw;
		height: 562rpx;
		position: fixed;
		top: 0;
		left: 0;
		z-index: 1;
	}
	.user-info-box {
		height: 190rpx;
		position: relative;
		z-index: 999;
		padding: 40rpx;
	}
	.info-box {
		background: #FFFFFF;
		box-shadow: 0px 10rpx 20rpx 0px rgba(49,49,51,0.05);
		border-radius: 10rpx;
		position: relative;
		z-index: 9999;
		margin: 0 30rpx;
	}
	.info-line {
		width: 4rpx;
		height: 24rpx;
		background: #1677FF;
		border-radius: 20rpx;
		margin-right: 20rpx;
	}
	.logout-btn {
		margin: 0 30rpx;
		height: 90rpx;
		background: #1677FF;
		border-radius: 10rpx;
		position: fixed;
		bottom: 40rpx;
		width: calc(100vw - 60rpx);
	}
</style>