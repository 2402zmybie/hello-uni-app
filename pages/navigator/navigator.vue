<template>
	<view>
		<view>导航跳转的学习</view>
		<navigator url="../detail/detail?id=80&question=aa">跳转至详情页</navigator>
		<navigator url="../message/message" open-type="switchTab">跳转到消息页面</navigator>
		<navigator url="../detail/detail" open-type="redirect">跳转详情页,关闭当前页面</navigator>
		<button @click="goDetail">跳转到详情页面</button>
		<button @click="redirectGoDetail">跳转到详情页面并关闭当前页面</button>
		<button @click="goMessage">跳转到信息页</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			goDetail() {
				//不关闭当前页面,跳转
				uni.navigateTo({
					url:'../detail/detail'
				})
			},
			//跳转到详情页面并关闭当前页面
			redirectGoDetail() {
				uni.redirectTo({
					url:'../detail/detail'
				})
			},
			goMessage() {
				//跳转到 tabBar 页面，并关闭其他所有非 tabBar 页面。
				uni.switchTab({
					url:'../message/message'
				})
			}
		},
		onUnload() {
			console.log("导航页面卸载了")
		}
	}
</script>

<style>

</style>
