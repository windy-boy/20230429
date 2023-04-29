<template>
	<view class="bg-white u-m-b-20">
		<view class="h-88 flex align-center">
			<image class="img-48 u-m-r-20"
				src="https://image.baidu.com/search/wisemiddetail?tn=wisemiddetail&ie=utf8&word=%E5%AE%85%E7%94%B7%E5%A5%B3%E7%A5%9E&pn=-4&size=mid&fr=wiseresult&fmpage=result&pos=imglist"
				mode=""></image>
			<view class="u-font-28 w-600" style="color: #3D3D3D;">
				蓝月湾花园12栋1单元15层1501
			</view>
		</view>
		<view class="fsl-box flex">
			<view class="flex-1">
				<view class=" u-m-b-24">
					<view class="sub-text">
						托管类型
					</view>
					<view class="sb-text">
						日租
					</view>
				</view>
				<view class="sub-text">
					<view class="">
						床型
					</view>
					<view class="sb-text">
						双人床
					</view>
				</view>
			</view>
			<view class="flex-1">
				<view class=" u-m-b-24">
					<view class="sub-text">
						出租状态
					</view>
					<view class="sb-text">
						空闲中
					</view>
				</view>
				<view class="sub-text">
					<view class="">
						面积
					</view>
					<view class="sb-text">
						100㎡
					</view>
				</view>
			</view>
			<view class="flex-1">
				<view class=" u-m-b-24">
					<view class="sub-text">
						收租时间
					</view>
					<view class="sb-text">
						每日
					</view>
				</view>
				<view class="sub-text">
					<view class="">
						地址
					</view>
					<view class="sb-text">
						上海市XX区XX路XX号
					</view>
				</view>
			</view>
		</view>
		<view class="footer-box">
			<view class="btn1">
				收入统计
			</view>
			<view class="btn1">
				图片视频
			</view>
			<view class="btn2">
				智能设备(3)
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		props: {
			info: Object
		},
		data() {
			return {

			}
		}
	}
</script>

<style lang="scss" scoped>
	.h-88 {
		height: 88rpx;
		border-bottom: 1px solid #E5E5E5;
	}

	.fsl-box {
		margin: 20rpx 30rpx;
		border-bottom: 1px solid #E5E5E5;
	}

	.sub-text {

		font-size: 24rpx;
		color: #989898;
		margin-bottom: 8rpx;
	}

	.sb-text {
		font-size: 24rpx;
		color: #333333;
	}

	.footer-box {
		height: 104rpx;
		display: flex;
		justify-content: flex-end;
	}

	.btn1 {
		width: 172rpx;
		height: 64rpx;
		border-radius: 10rpx;
		border: 1px solid #B2B2B2;
		display: flex;
		align-items: center;
		justify-content: center;
		font-size: 26rpx;
		color: #656565;
		margin-right: 20rpx;
	}

	.btn2 {
		width: 172rpx;
		height: 64rpx;
		border-radius: 10rpx;
		background: #1677FF;
		display: flex;
		align-items: center;
		justify-content: center;
		font-size: 26rpx;
		color: #fff;
		margin-right: 30rpx;
	}
</style>
