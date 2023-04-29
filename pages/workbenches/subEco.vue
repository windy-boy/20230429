<template>
	<view class="u-p-l-30 u-p-r-30 u-p-t-20 u-p-b-20">
		<view class="bg-white u-p-30">
			<view class="flex align-center u-m-b-30">
				<text class="u-font-30 c-000 w-600 u-m-r-30">上传打扫照片</text>
				<text class="c-b2 u-font-24">最多可上传9张</text>
			</view>
			<view class="flex flex-wrap">
				<u-upload :fileList="fileList1" @afterRead="afterRead" @delete="deletePic" name="1" multiple
					:maxCount="9"></u-upload>
			</view>
			<view class="blank-line">

			</view>
			<view class="blank-title flex align-center">
				<text class="u-font-30 c-000 w-600 u-m-r-30">备注</text>
				<text class="c-b2 u-font-24">选填</text>
			</view>
			<u--textarea v-model="value" placeholder="请输入" count :maxlength="200" height="120"></u--textarea>
		</view>
		<view class="sub-btn c-white u-font-32 flex align-center justify-center" @tap="handleSubmit">
			提交
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				fileList1: [],
				value:""
			}
		},
		methods: {
			// 删除图片
			deletePic(event) {
				this[`fileList${event.name}`].splice(event.index, 1)
			},
			// 新增图片
			async afterRead(event) {
				// 当设置 multiple 为 true 时, file 为数组格式，否则为对象格式
				let lists = [].concat(event.file)
				let fileListLen = this[`fileList${event.name}`].length
				lists.map((item) => {
					this[`fileList${event.name}`].push({
						...item,
						status: 'uploading',
						message: '上传中'
					})
				})
				for (let i = 0; i < lists.length; i++) {
					const result = await this.uploadFilePromise(lists[i].url)
					let item = this[`fileList${event.name}`][fileListLen]
					this[`fileList${event.name}`].splice(fileListLen, 1, Object.assign(item, {
						status: 'success',
						message: '',
						url: result
					}))
					fileListLen++
				}
			},
			uploadFilePromise(url) {
				return new Promise((resolve, reject) => {
					let a = uni.uploadFile({
						url: 'https://api.u-market.cn/merchant/util/upload', // 仅为示例，非真实的接口地址
						filePath: url,
						name: 'file',
						formData: {
							user: 'test'
						},
						success: (res) => {
							setTimeout(() => {
								resolve(res.data.data)
							}, 1000)
						}
					});
				})
			},
			handleSubmit() {
				uni.showToast({
					title:'提交成功'
				})
			}
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

	::v-deep {
		.u-upload__button {
			width: 180rpx !important;
			height: 180rpx !important;
		}

		.u-upload__wrap__preview__image {
			width: 180rpx !important;
			height: 180rpx !important;
		}
	}

	.blank-line {
		border-bottom: 1px solid #EDEDED;
	}

	.blank-title {
		height: 92rpx;
	}
	.sub-btn {
		height: 80rpx;
		background: #1677FF;
		border-radius: 10px 10px 10px 10px;
		margin-top: 60rpx;
	}
</style>
