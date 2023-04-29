<template>
	<view class="page-container">
		<scroll-view scroll-y="true" >
			<view>
				<image class="img-420" src="../../static/home-top-bg.png" mode=""></image>
				<view class="" :style="{height: statusHeight + 'px'}">
					
				</view>
				<view class="u-p-30 th-head text-center c-white" @tap="handleTo">
					<view class="u-m-b-10 w-500 u-font-64 ">
						24
					</view>
					<view class="u-font-26">
						待打扫房屋
					</view>
				</view>
				<view class="work-benches-container">
					<image class="white-opt" src="../../static/white-opt.png" mode=""></image>
					<view class="tab-view flex u-font-30 c-65">
						<view class="tab-view-item flex-1 flex align-center justify-center" @tap="handleClick(item.value)" :class="{active: tabIndex === item.value}" v-for="item in tabList" :key="item.value">
							{{item.name}}
							<view class="tab-line" v-if="tabIndex === item.value">
								
							</view>
						</view>
						
					</view>
					<view class="u-p-l-30 u-p-r-30" v-for="item in list" :key="item">
						<view class="list-title flex align-center u-m-b-20">
							<view class="list-line">
								
							</view>
							<text class="u-m-l-10">蓝月湾花园12栋1单元</text>
						</view>
						<workbenchesItem></workbenchesItem>
					</view>
				</view>
			</view>
		</scroll-view>

	</view>
</template>

<script>
	import workbenchesItem from './child/item.vue'
	export default {
		components:{
			workbenchesItem,
		},
		data() {
			return {
				statusHeight: 44,
				tabIndex:0,
				tabList:[
					{
						name:'默认',
						value:0
					},
					{
						name:'小区名',
						value:1
					},
					{
						name:'楼栋',
						value:2
					},
					{
						name:'单元',
						value:3	
					},
				],
				list:[1,2]
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
					url:'/pages/workbenches/waitClean'
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
	.img-420 {
		width: 100vw;
		height: 380rpx;
		position: fixed;
		top: 0;
		left: 0;
		z-index: 1;
	}
	.th-head {
		position: relative;
		z-index: 2;
	}
	.work-benches-container {
		position: relative;
		z-index: 2;
		margin-top: 30rpx;
		background-color: #F7F7F7;
		.white-opt {
			width: 100%;
			height: 180rpx;
			position: relative;
			z-index: 3;
		}
		.tab-view {
			width: 100%;
			height: 90rpx;
			position: absolute;
			left: 0;
			top:0;
			z-index: 5;
			border-radius: 20rpx;
			.tab-view-item {
				position: relative;
				.tab-line {
					width: 32rpx;
					height: 6rpx;
					background: #1677FF;
					border-radius: 4rpx 4rpx 4rpx 4rpx;
					position: absolute;
					bottom: 0;
					left: 50%;
					transform: translateX(-50%);
				}
			}
			
		}
	}
	.c-65 {
		color:#656565;
	}
	.active {
		color: #1677FF;
	}
	.list-title {
			font-weight: 500;
			color: #3D3D3D;
			.list-line {
				width: 6rpx;
				height: 24rpx;
				background: #1677FF;
				border-radius: 20prx 20rpx 20rpx 20rpx;
			}
	}
</style>