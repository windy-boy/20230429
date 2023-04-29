<template>
	<view class="trusteeship-container">
		<image class="bg-img" src="../../static/trusteeship.png" mode=""></image>
		<view class="h-190 u-p-t-40">
			<view class="u-font-48 w-500 c-000 u-m-b-4">
				我想托管
			</view>
			<view class="u-font-26 c-80">
				免费托管 轻松收租
			</view>
		</view>
		<view class="bg-white border-raidus-20 u-p-l-30 u-p-r-30 z-index-999">
			<view class="h-100 flex align-center">
				<view class="w-178 u-font-30">
					所在地
				</view>
				<view class="flex-1">
					请选择
				</view>
				<image class="img-32" src="../../static/grey-arrow.png" mode=""></image>
			</view>
			<view class="h-100 flex align-center">
				<view class="w-178 u-font-30">
					小区名称
				</view>
				<view class="flex-1">
					<input v-model="form.name" placeholder="请输入" />
				</view>
			</view>
			<view class="h-100 flex align-center">
				<view class="w-178 u-font-30">
					楼栋
				</view>
				<view class="flex-1" @tap="show = true">
					请选择
				</view>
				<image class="img-32" src="../../static/grey-arrow.png" mode=""></image>
			</view>
			<view class="h-100 flex align-center">
				<view class="w-178 u-font-30">
					单元
				</view>
				<view class="flex-1">
					请选择
				</view>
				<image class="img-32" src="../../static/grey-arrow.png" mode=""></image>
			</view>
			<view class="h-100 flex align-center">
				<view class="w-178 u-font-30">
					楼层
				</view>
				<view class="flex-1">
					请选择
				</view>
				<image class="img-32" src="../../static/grey-arrow.png" mode=""></image>
			</view>
			<view class="h-100 flex align-center">
				<view class="w-178 u-font-30">
					房号
				</view>
				<view class="flex-1">
					<input v-model="form.name" placeholder="请输入" />
				</view>
			</view>
			<view class="h-100 flex align-center">
				<view class="w-178 u-font-30">
					床型
				</view>
				<view class="flex-1">
					请选择
				</view>
				<image class="img-32" src="../../static/grey-arrow.png" mode=""></image>
			</view>
			<view class="h-100 flex align-center">
				<view class="w-178 u-font-30">
					面积
				</view>
				<view class="flex-1">
					<input v-model="form.name" placeholder="请输入" />
				</view>
				m²
			</view>
			<view class="h-100-1 flex align-center">
				<view class="w-178 u-font-30">
					托管类型
				</view>
				<view class="flex-1">
					请选择
				</view>
				<image class="img-32" src="../../static/grey-arrow.png" mode=""></image>
			</view>
		</view>
		<view class="sub-btn flex align-center justify-center">
			<text class="c-white u-font-32">提交</text>
		</view>

		<u-picker :show="show" ref="uPicker" :columns="columns" @confirm="confirm"  @cancel="show = false"></u-picker>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				columns: [
					['深圳', '厦门', '上海', '拉萨']
				],
				show: false,
				form: {
					name:""
				}
			}
		},
		methods: {
			changeHandler(e) {
				const {
					columnIndex,
					value,
					values, // values为当前变化列的数组内容
					index,
					// 微信小程序无法将picker实例传出来，只能通过ref操作
					picker = this.$refs.uPicker
				} = e
				// 当第一列值发生变化时，变化第二列(后一列)对应的选项
				if (columnIndex === 0) {
					// picker为选择器this实例，变化第二列对应的选项
					picker.setColumnValues(1, this.columnData[index])
				}
			},
			// 回调参数为包含columnIndex、value、values
			confirm(e) {
				console.log('confirm', e)
			 this.show = false
			}
		}
	}
</script>

<style lang="scss" scoped>
	.trusteeship-container {
		background: #F7F7F7;
		position: relative;

		.bg-img {
			width: 284rpx;
			height: 284rpx;
			position: absolute;
			top: 0;
			right: 30rpx;
			z-index: 1;
		}

		.h-190 {
			height: 190rpx;
			padding-left: 30rpx;
		}
	}

	.c-000 {
		color: #000;
	}

	.c-80 {
		color: #808080;
	}

	.h-100 {
		height: 100rpx;
		border-bottom: 1px solid #E5E6EB;
	}

	.h-100-1 {
		height: 100rpx;
	}

	.w-178 {
		width: 178rpx;
		color: #1D2129;
	}

	.z-index-999 {
		position: relative;
		z-index: 999;
		margin-top: -30rpx;
		margin: 0 30rpx;
	}

	.sub-btn {
		margin: 60rpx 30rpx;
		height: 80rpx;
		background: #1677FF;
		border-radius: 10rpx;
		opacity: 1;
	}
</style>
