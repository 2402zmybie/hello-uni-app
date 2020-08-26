<template>
	<view>
		<view>一进入页面就发送GET请求</view>
		<button @click="postClick">发送POST请求</button>
		<button @click="setStorage">存储数据</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				'get_chapter':'https://wanandroid.com/wxarticle/chapters/json',
				'register_url':'https://www.wanandroid.com/user/register'
			}
		},
		methods: {
			postClick() {
				uni.request({
					url:this.register_url,
					method:'POST',
					data:{
						'username':'he',
						'password':'123456',
						'repassword':'123456',
					},
					success: (res)=> {
						console.log(res)
						
					}
				})
			},
			setStorage() {
				//向本地存储数据
				uni.setStorage({
					key:'username',
					data:'老何',
					success() {
						console.log('存储成功')
					}
				})
			}
		},
		// onShow() {
		// 	uni.request({
		// 		url:this.get_chapter,
		// 		method:'GET',
		// 		success:(res)=> {
		// 			console.log(res)
		// 		}
		// 	})
		// }
	}
</script>

<style>

</style>
