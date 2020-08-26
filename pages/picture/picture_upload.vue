<template>
	<view>
		<button @click="chooseImg">上传图片</button>
		<image class="show_image" v-for="(item,index) in imgArr" :src="item" mode="aspectFit" @click="previewImg(index)"></image>
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
		}
	}
</script>

<style>
.show_image {
	
}
</style>
