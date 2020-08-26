<template>
	<view class="content">
		<!-- 3 使用组件 -->
		<test v-if="flag"></test>
		<button @click="btnClick" type="primary">组件显示和隐藏</button>
	</view>
</template>

<script>
	//1 导入组件
	import test from '../../components/test.vue'
	export default {
		data() {
			return {
				flag:true
			}
		},
		onLoad() {

		},
		methods: {
			btnClick() {
				this.flag = !this.flag
			}
		},
		//2 注册节点
		components:{
			test
		}
	}
</script>

<style>
	
</style>
