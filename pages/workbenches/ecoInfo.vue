<template>
	<view class="u-p-l-30 u-p-r-30 u-p-t-20 u-p-b-20">
		<view class="bg-white u-p-30">
			<view class="flex align-center u-m-b-30">
				<text class="u-font-30 c-000 w-600 u-m-r-30">打扫照片</text>
			</view>
			<view class="blank-line">
				<view class="flex flex-wrap">
					<view class="" v-for="(item, index) in list" :key="index">
						<image class="eco-img" src="../../static/home-top-bg.png" mode=""></image>
					</view>
				</view>
			</view>
			<view class="blank-title flex align-center">
				<text class="u-font-30 c-000 w-600 u-m-r-30">备注</text>
			</view>
			<view class="u-font-28 c-80">
				这里是备注文字，这里是备注文字，这里是备注文字，这里是备注文字，这里是备注文字，这里是备注文字，这里是备注文字，这里是备注文字，这里是备注文字，这里是备注文字，这里是备注文字，这里是备注文字。
			</view>
		</view>
		<view class="u-m-t-20 eco-info u-p-30">
			<view class="u-font-26 c-98 flex align-center u-m-b-20">
				<text>打扫编号：</text>
				<text>DH2023020100001</text>
			</view>
			<view class="u-font-26 c-98 flex align-center u-m-b-20">
				<text>要求打扫日期：</text>
				<text>2023-02-01</text>
			</view>
			<view class="u-font-26 c-98 flex align-center ">
				<text>实际打扫时间：</text>
				<text>2023-02-01 12:00:00</text>
			</view>
		</view>
	</view>

	
</template>

<script>
	export default {
		data() {
			return {
				list: [1, 1, 1, 1, 1, 1, 1, 1, 1]
			}
		},
		methods: {

		},

	}
</script>

<style lang="scss" scoped>
	.c-000 {
		color: #000;
	}

	.c-b2 {
		color: #B2B2B2;
	}

	.c-98 {
		color: #989898;
	}

	.blank-line {
		border-bottom: 1px solid #EDEDED;
	}

	.blank-title {
		height: 92rpx;
	}

	.eco-img {
		width: 180rpx;
		height: 180rpx;
		margin-left: 20rpx;
		margin-bottom: 20rpx;
	}

	.c-80 {
		color: #808080;
	}

	.eco-info {
		background: #FFFFFF;
		border-radius: 20rpx;
	}
</style>
