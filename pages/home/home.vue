<template>
	<view>
		<view>数据绑定的学习</view>
		<view>{{ msg }}</view>
		<view>{{ "你好" + num }}</view>
		<view>{{ 1 + 1 }}</view>
		<view>{{ flag?"我是真的":"我是假的" }}</view>
	</view>
</template>

<script>
	export default{
		data() {
			return {
				msg:'hello',
				num:1,
				flag: true
			}
		},
		methods:{
			
		}
	}
</script>

<style>

</style>
