<template>
	<view class="page-container">
		<scroll-view scroll-y="true">
			<view>
				<image class="img-580" src="../../static/house_bg.png" mode=""></image>
				<view class="" :style="{height: statusHeight + 'px'}">

				</view>
				<view class="th-head flex c-white u-m-b-50">
					<view class="flex-1 u-p-r-10">
						<view class="u-font-48 w-500 u-m-b-6">
							48
						</view>
						<view class="u-font-24">
							房产总数
						</view>
					</view>
					<view class="flex-1 u-p-r-10">
						<view class="u-font-48 w-500 u-m-b-6">
							120000.00
						</view>
						<view class="u-font-24">
							今日可收房租
						</view>
					</view>
					<view class="flex-1 u-p-r-10">
						<view class="u-font-48 w-500 u-m-b-6">
							8999.00
						</view>
						<view class="u-font-24">
							可提现房租总余额
						</view>
					</view>
				</view>
				<view class="flex align-center justify-between position-box u-m-b-60">
					<view class="white-btn flex align-center justify-center u-font-24">
						我想托管
					</view>
					<view class="white-btn flex align-center justify-center u-font-24">
						解除托管
					</view>
					<view class="white-btn flex align-center justify-center u-font-24">
						查看房产
					</view>
					<view class="white-btn flex align-center justify-center u-font-24">
						查收房租
					</view>
				</view>
				<view class="u-p-30 bg-white border-raidus-20">
					<view class="flex align-center bg-f2 border-raidus-10">
						<image class="img-32 u-m-r-10" src="../../static/grey_search.png" mode=""></image>
						<input v-model="searchKey"/>
					</view>
				</view>
				<view class="u-p-30">
					<Item v-for="item in list" :key="item"></Item>
				</view>
			</view>
		</scroll-view>

	</view>
</template>

<script>
	import Item from './child/item.vue'
	export default {
		components: {
Item
		},
		data() {
			return {
				statusHeight: 44,
				tabIndex: 0,
				searchKey:"",
				tabList: [{
						name: '默认',
						value: 0
					},
					{
						name: '小区名',
						value: 1
					},
					{
						name: '楼栋',
						value: 2
					},
					{
						name: '单元',
						value: 3
					},
				],
				list: [1, 2]
			}
		},
		onLoad() {
			const res = uni.getSystemInfoSync()
			this.statusHeight = this.statusHeight + res.statusBarHeight
		},
		methods: {
			handleClick(val) {
				this.tabIndex = val
			},
			handleTo() {
				uni.navigateTo({
					url: '/pages/workbenches/waitClean'
				})
			}
		}
	}
</script>

<style lang="scss" scoped>
	.page-container {
		width: 100%;
		height: 100%;
		background: #F7F7F7;
	}

	.img-580 {
		width: 100vw;
		height: 580rpx;
		position: fixed;
		top: 0;
		left: 0;
		z-index: 1;
	}

	.th-head {
		position: relative;
		z-index: 2;
		padding: 40rpx 30rpx 50rpx;
	}

	.position-box {
		position: relative;
		z-index: 2;
		padding: 0 30rpx;
	}

	.white-btn {
		width: 160rpx;
		height: 64rpx;
		background: #FFFFFF;
		border-radius: 10rpx;
		color: #1677FF;
	}
	.border-raidus-20 {
		border-radius: 20rpx;
		position: relative;
		z-index: 999;
		margin: 0 20rpx;
	}
	.border-raidus-10 {
		border-radius: 10rpx;
		padding: 12rpx 24rpx;
	}
	.bg-f2 {
		background: #F2F3F5;
	}
</style>
