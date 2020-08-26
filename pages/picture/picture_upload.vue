<template>
	<view>
		<button @click="chooseImg">上传图片</button>
		<image class="show_image" v-for="(item,index) in imgArr" :src="item" mode="aspectFit" @click="previewImg(index)"></image>
		<!-- #ifdef H5 -->
		<view>我希望只在H5中看见</view>
		<!-- #endif -->
		<!-- #ifdef MP-WEIXIN -->
		<view>我希望只在微信小程序中看见</view>
		<!-- #endif -->
		<!-- #ifdef APP-PLUS -->
		<view>我希望只在APP-PLUS中看见</view>
		<!-- #endif -->
		<!-- #ifdef APP-VUE -->
		<view>我希望只在APP-VUE中看见</view>
		<!-- #endif -->
		<view class="text-dif">测试不同设备样式不同</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				imgArr:[]
			}
		},
		methods: {
			chooseImg() {
				uni.chooseImage({
					count:5,
					success:(res)=> {
						console.log(res)
						this.imgArr = res.tempFilePaths
					}
				})
			},
			//图片预览
			previewImg(index) {
				console.log(index)
				uni.previewImage({
					current:index,
					urls:this.imgArr,
					loop:true,
					indicator:'number'
				})
			}
		},
		onLoad() {
			// #ifdef APP-PLUS
			console.log("我希望app中打印")
			// #endif
			// #ifdef H5
			console.log("我希望H5中打印")
			// #endif
		}
	}
</script>

<style>
.text-dif {
	/* #ifdef APP-PLUS */
	color: #f00;
	/* #endif */
	/* #ifdef H5 */
	color: #007AFF;
	/* #endif */
}
</style>
