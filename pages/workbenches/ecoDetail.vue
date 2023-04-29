<template>
	<view class="eco-page">
		<topBack></topBack>
		<swiper class="u-rela" :indicator-dots="false" :autoplay="true" :interval="5000" :duration="1000">
			<swiper-item>
				<image class="swiper-img" src="../../static/home-top-bg.png" mode="aspectFill"></image>
			</swiper-item>
			<swiper-item>
				<image src="../../static/tabbar1_active.png" mode=""></image>
			</swiper-item>
			
			<view class="swiper-count flex align-center justify-center c-white u-font-24">
				<text class="u-font-32">1</text>/5
			</view>
		</swiper>
		
		<view class="eco-container">
			<view class="eco-box bg-white">
				<view class="eco-head flex align-center">
					<view class="status-box c-white u-font-24 u-m-r-10">待打扫</view>
					<view class="w-600 u-font-28">
						蓝月湾花园12栋1单元15层1501
					</view>
				</view>
				<view class="eco-line">
					
				</view>
				<view class="flex u-m-b-40">
					<view class="flex-1 u-font-24">
						<view class="e-98 u-m-b-4">
							托管类型
						</view>
						<view class="c-333 w-600">
							XXXX
						</view>
					</view>
					<view class="flex-1 u-font-24">
						<view class="e-98 u-m-b-4">
							出租状态
						</view>
						<view class="c-333 w-600">
							XXXX
						</view>
					</view>
				</view>
				<view class="flex u-m-b-40">
					<view class="flex-1 u-font-24">
						<view class="e-98 u-m-b-4">
							打扫原因
						</view>
						<view class="c-333 w-600">
							XXXX
						</view>
					</view>
					<view class="flex-1 u-font-24">
						<view class="e-98 u-m-b-4">
							床型
						</view>
						<view class="c-333 w-600">
							XXXX
						</view>
					</view>
				</view>
				<view class="flex u-p-b-30">
					<view class="flex-1 u-font-24">
						<view class="e-98 u-m-b-4">
							面积
						</view>
						<view class="c-333 w-600">
							XXXX
						</view>
					</view>
					<view class="flex-1 u-font-24">
						<view class="e-98 u-m-b-4">
							地址
						</view>
						<view class="c-333 w-600">
							XXXX
						</view>
					</view>
				</view>
			</view>
			<view class="sub-btn flex align-center justify-center c-white w-600 u-font-30" @tap="handleSubmit">
				打扫完成
			</view>
			<view class="detail-btn flex align-center justify-center c-333 w-600 u-font-30" @tap="handeTo">
				打扫详情
			</view>
		</view>
		
	</view>
</template>

<script>
	export default {
		components: {

		},
		data() {
			return {

			}
		},
		methods: {
			handleSubmit() {
				uni.navigateTo({
					url:'/pages/workbenches/subEco'
				})
			},
			handeTo() {
				uni.navigateTo({
					url:'/pages/workbenches/ecoInfo'
				})
			}
		}
	}
</script>

<style lang="scss" scoped>
	.eco-page {
		min-height: 100vh;
		background-color: #F7F7F7;
	}
::v-deep {
	swiper  {
		height: 750rpx;
	}
}
.swiper-img {
	width: 100%;
	height: 750rpx;
}
.eco-container {
	padding: 0 30rpx;
	margin-top: -30rpx;
	position: relative;
	z-index: 999;
	.eco-box{
		border-radius: 20rpx;
		padding: 0 30rpx;
		.eco-head {
			height: 100rpx;
			.status-box {
				padding: 4rpx 10rpx;
				border-radius: 4rpx;
				background: #1677FF;
			}
		}
		.eco-line{
			width: 100%;
			height: 1px;
			background-color: #EDEDED;
			margin-bottom: 30rpx;
		}
	}
}
.swiper-count {
	position: absolute;
	bottom: 60rpx;
	right: 30rpx;
	border-radius: 24rpx;
	background-color: rgba(0, 0, 0, 0.3);
	width: 100rpx;
	height: 48rpx;
}
.e-98 {
	color: #989898
}
.sub-btn {
	height: 80rpx;
	background: #1677FF;
	opacity: 1;
	border-radius: 10rpx;
	margin-top: 30rpx;
}
.detail-btn {
	height: 80rpx;
	opacity: 1;
	border: 1px solid #CCCCCC;
	border-radius: 10rpx;
	margin-top: 30rpx;
}
</style>
