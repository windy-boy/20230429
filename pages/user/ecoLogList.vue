<template>
	<view class="">
		<image class="img-600" src="../../static/eco-bg.png" mode=""></image>
		<view class="" :style="{height: statusHeight + 'px'}">
			
		</view>
		<view class="u-p-l-30 u-p-r-30 eco-rela">
			<view class="log-title u-font-40 w-600 c-white flex align-center">
				打扫明细
			</view>
			<view class="u-m-b-30 flex align-center c-white u-font-24">
				<view class="flex-1 flex align-center" @tap="show = true">
					<text class="u-font-26">2023年3月</text>
					<image class="img-40" src="../../static/white-arrow.png" mode=""></image>
				</view>
				<view class="u-m-r-30">
					<text>总金额: </text>
					<text class="w-600">¥9000.00</text>
				</view>
				<view class="">
					<text>总房屋数量: </text>
					<text class="w-600">9999</text>
				</view>
			</view>
			<view class="list-container bg-white">
				<view class="list-itme" v-for="(item, index) in list" :key="index" :class="{'box-shaow': index !== list.length - 1}" @tap="handleTo(item)">
					<view class="flex u-m-b-10 c-333">
						<view class="flex-1 u-font-28">
							单人床
						</view>
						<view class="u-font-36">
							80.00
						</view>
					</view>
					<view class="flex align-center u-font-24" style="color: #B2B2B2;">
						<view class="flex-1 u-m-r-10">
							蓝月湾花园12栋1单元15层1501
						</view>
						<view class="">
							2023-03-01 11:00:00
						</view>
					</view>
				</view>
			</view>
		</view>
		
		<!-- 日期选择器 -->
		 <u-datetime-picker
		                :show="show"
		                v-model="searchTime"
		                mode="year-month"
						@cancel="show =false"
						@confirm="handleChangeTime"
		        ></u-datetime-picker>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				statusHeight: 44,
				show:false,
				searchTime:Number(new Date()),
				list:[1,2,3,4,5,6]
			}
		},
		onLoad() {
			const res = uni.getSystemInfoSync()
			this.statusHeight = this.statusHeight + res.statusBarHeight
		},
		methods: {
			handleChangeTime(val) {
					const time = new Date(val.value);
					const y = time.getFullYear();
					const m = time.getMonth()+1;
					console.log(val,'val', y, m)
					this.show = false
			},
			handleTo() {
				uni.navigateTo({
					url:'/pages/workbenches/ecoInfo'
				})
			}
		}
	}
</script>

<style lang="scss" scoped>
	.img-600 {
		width: 100vw;
		height: 600rpx;
		position: fixed;
		top: 0;
		left: 0;
		z-index: 1;
	}
	.log-title {
		height: 118rpx;
	}
	.eco-rela {
		position: relative;
		z-index: 99;
	}
	.list-container {
		border-radius: 20rpx;
		padding: 0 30rpx;
	}
	.list-itme {
		padding: 30rpx 0;
	}
	.box-shaow {
		box-shadow: inset 0px -1px 0px 0px #DFE3E5;
	}
</style>