<template>
	<view class="bg-white workbenches-item u-m-b-20">
		<view class="workbenches-item--head flex justify-between align-center u-p-l-30 u-p-r-30">
			<view class="w-600">
				<text v-if="info.type === 1">单床({{info.typeCount}})</text>
				<text v-else>双床({{info.typeCount}})</text>
			</view>
			<view class="flex align-center" style="color: #656565;">
				<view class="u-m-r-30">
					空({{info.emptyCount}})     
				</view>
				<view class="u-m-r-30">
					     脏({{info.dirtyCount}})
				</view>
				<view class="">
					可售数({{info.cellCount}})
				</view>
			</view>
		</view>
		<view class="workbenches-item--body flex flex-wrap">
			<view class="wib-item flex align-center justify-center" @tap="handleTo(item)" v-for="(item,index) in info.list" :key="index" :class="{'u-m-r-18': (index+1) % 4 !== 0}">
				<image class="img-48 wib-item--img" v-if="isEmpty" src="../../../static/disty.png" mode=""></image>
				<image class="img-48 wib-item--img" v-else src="../../../static/empty.png" mode=""></image>
				{{item.name}}
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		props: {
			info: {
				type:Object,
				default:() => {
					return {
						type: 1,// 1单床 2双床
						typeCount: 10,//床数量
						emptyCount: 7,//空
						dirtyCount: 2,//脏
						cellCount: 1, // 可销售
						isEmpty:true,
						list:[
							{
								name: 101,
							},
							{
								name: 101,
							},
							{
								name: 101,
							},
							{
								name: 101,
							},
							{
								name: 101,
							},
						]
					}
				}
			}
		},
		data(){
			return {
				
			}
		},
		methods: {
			handleTo() {
				uni.navigateTo({
					url:'/pages/workbenches/ecoDetail'
				})
			}
		}
	}
</script>

<style lang="scss" scoped>
	.workbenches-item {
		border-radius: 20rpx;
		overflow: hidden;
		&--head {
			height: 80rpx;
			color: #3D3D3D;
			box-shadow: inset 0px -1px 0px 0px #E5E6EB;
		}
		&--body {
			padding: 20rpx 30rpx 30rpx;
			flex-wrap: wrap;
			.wib-item {
				flex: 0 0 calc((100% - 54rpx - 18rpx) / 4);
				height: 80rpx;
				position: relative;
				border: 1px solid #CCCCCC;
				border-radius: 6rpx;
				margin-bottom: 18rpx;
				&--img {
					position: absolute;
					top: 0;
					right: 0;
				}
			}
		}
	}
</style>