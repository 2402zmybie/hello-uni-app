<template>
	<view>
		<view>一进入页面就发送GET请求</view>
		<button @click="postClick">发送POST请求</button>
		<button @click="setStorage">存储数据</button>
		<button @click="getStorage">获取数据</button>
		<button @click="removeStorage">移除数据</button>
		<button @click="setStorageSync" type="primary">将 data 存储在本地缓存中指定的 key 中，会覆盖掉原来该 key 对应的内容，这是一个同步接口</button>
		<button @click="getStorageSync">getStorageSync</button>
		<button @click="removeStorageSync">removeStorageSync</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				get_chapter:'https://wanandroid.com/wxarticle/chapters/json',
				register_url:'https://www.wanandroid.com/user/register'
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
			},
			getStorage() {
				uni.getStorage({
					key:'username',
					success(res) {
						console.log("获取key为username的数据成功:"+ res.data)
					}
				})
			},
			removeStorage() {
				uni.removeStorage({
					key:'username',
					success: function (res) {
					        console.log('移除key为username的数据成功');
					    }
				})
			},
			setStorageSync() {
				//同步存储键值对
				uni.setStorageSync("id","1")
			},
			//同步获取数据接口
			getStorageSync() {
				var id = uni.getStorageSync("id")
				console.log(id)
			},
			removeStorageSync() {
				uni.removeStorageSync("id")
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
