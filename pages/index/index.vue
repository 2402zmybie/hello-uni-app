<template>
	<view class="content">
		<!-- 3 使用组件 -->
		<test v-if="flag" :title="title" @myEvent="getNumFromChildren"></test>
		<view >子组件传递的数据{{ num }}</view>
		<button @click="btnClick" type="primary">组件显示和隐藏</button>
		<view style="margin-top: 50rpx;">父子组件传值示范区域</view>
		<test-a></test-a>
		<test-b></test-b>
		<uni-calendar 
		:insert="true"
		:lunar="true" 
		:start-date="'2019-3-2'"
		:end-date="'2019-5-20'"
		@change="change"
		 />
		
	</view>
</template>

<script>
	//1 导入组件
	import test from '../../components/test.vue'
	import testA from '../../components/a.vue'
	import testB from '../../components/b.vue'
	import uniCalendar from '@/components/uni-calendar/uni-calendar.vue'
	export default {
		data() {
			return {
				flag:true,
				title:'hellow',
				num:0
			}
		},
		onLoad() {

		},
		methods: {
			btnClick() {
				this.flag = !this.flag
			},
			getNumFromChildren(num) {
				console.log('子组件发送的数据' + num)
				this.num = num
			},
			change(e) {
				console.log('组件插件选择日期', e)
				console.log('日期',e.fulldate)
			}
		},
		//2 注册节点
		components:{
			test,
			'test-a':testA,
			'test-b':testB,
			 uniCalendar
		}
	}
</script>

<style>
	
</style>
