<template>
	<view class="u-p-l-30 u-p-r-30 u-p-t-20 u-p-b-20">
		<view class="">
			<view class="msg-box u-p-30 bg-white u-m-b-20" v-for="(item, index) in list" :key="index">
				<view class="flex u-m-b-26">
					<view class="flex-1 flex align-center">
						<text class="u-font-32 c-333">这里是消息标题</text>
						<view class="red-box u-m-l-6">
							
						</view>
					</view>
					<view class="u-font-26" style="color: #A7AAB2;">
2023-02-01 10:30
					</view>
				</view>
				<view class="u-font-26" style="color: #A7AAB2">
					这里是系统消息的内容文字。这里是系统消息的内容文字。这里是系统消息的内容文字。这里是系统消息的内容文字。这里是系统消息的内容文字。这里是系统消息的内容文字。
				</view>
				<view class="u-m-t-44 flex align-center" style="justify-content: flex-end;color: #919298;" v-if="item.type === 2">
					<text class="u-font-26">查看详情</text>
					<image class="img-32 u-m-l-12" src="../../static/grey-arrow.png" mode=""></image>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list: [{
						type: 1,
					},
					{
						type: 2
					}
				]
			}
		}
	}
</script>

<style lang="scss" scoped>
	.msg-box {
		border-radius: 6rpx;
	}
	.red-box {
		width: 24rpx;
		height: 24rpx;
		background: #FB5543;
		border-radius: 50%;
	}
</style>
