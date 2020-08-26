<template>
	<view>
		<button @click="addNum">修改b组件的数据</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		},
		methods:{
			addNum() {
				//在一个页面发送全局事件
				uni.$emit('updateNum',10)
			}
		}
	}
</script>

<style>

</style>
