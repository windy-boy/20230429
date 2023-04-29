<template>
	<view class="">
		<view class="tab-list flex align-center">
			<view class="flex-1 flex align-center justify-center u-rela tab-item" v-for="item in tabList"
				:key="item.value" @tap="handleClick(item.value)">
				<text :class="{'c-blue': item.value === tabIndex}">{{item.name}}</text>
				<view class="tab-line" v-if="item.value === tabIndex">

				</view>
			</view>

		</view>
		<scroll-view scroll-y="true" class="scroll-view-container u-p-t-30">
			<view class="u-p-l-30 u-p-r-30" v-for="item in list" :key="item">
				<view class="list-title flex align-center u-m-b-20">
					<view class="list-line">

					</view>
					<text class="u-m-l-10">蓝月湾花园12栋1单元</text>
				</view>
				<workbenchesItem></workbenchesItem>
			</view>
		</scroll-view>
	</view>
</template>

<script>
	import workbenchesItem from './child/item.vue'
	export default {
		components: {
			workbenchesItem,
		},
		data() {
			return {
				tabIndex: 1,
				tabList: [{
						name: '默认',
						value: 1
					},
					{
						name: '小区名',
						value: 2
					},
					{
						name: '楼栋',
						value: 3
					},
					{
						name: '单元',
						value: 4
					},
				],
				list: [1, 2, 3, 4, 5, 6, 7, 8, 9, 0]
			}
		},
		methods: {
			handleClick(val) {
				this.tabIndex = val
			}
		}
	}
</script>

<style lang="scss" scoped>
	.tab-list {
		width: 100%;
		height: 90rpx;
		color: #656565;
		font-weight: 500;

		.tab-item {
			height: 90rpx;
		}

		.tab-line {
			position: absolute;
			bottom: 0;
			left: 50%;
			transform: translateX(-50%);
			width: 32rpx;
			height: 6rpx;
			background: #1677FF;
			border-radius: 4rpx;
		}
	}

	.scroll-view-container {
		height: calc(100vh - 92rpx);
		background: #F7F7F7;
	}
</style>
