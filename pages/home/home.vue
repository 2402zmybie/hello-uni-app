<template>
	<view>
		<view>数据绑定的学习</view>
		<view>{{ msg }}</view>
		<view>{{ "你好" + num }}</view>
		<view>{{ 1 + 1 }}</view>
		<view>{{ flag?"我是真的":"我是假的" }}</view>
		<image :src="imageUrl"></imaeg>
		<view v-for="(item,index) in arr" :key="index" @click="itemClick(index)">序号:{{item.id}}, 名字:{{ item.name }}, 年龄:{{ item.age }}</view>
		<button @click="clickHandle(20,$event)"type="primary">注册点击事件</button>
	</view>
</template>

<script>
	export default{
		data() {
			return {
				msg:'hello',
				num:1,
				flag: true,
				imageUrl: 'https://dss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=286994928,1256587823&fm=26&gp=0.jpg',
				arr:[{
					"name":'宋小宝',
					age:20,
					id:1
				}, {
					"name":'宋大宝',
					age:20,
					id:1
				},{
					"name":'宋三宝',
					age:20,
					id:1
				}]
			}
		},
		methods:{
			//num是传递过来的参数, e是事件对象
			clickHandle(num,e) {
				console.log("点击了",num,e)
			},
			itemClick(index) {
				console.log("点击列表" + index)
			}
			
		}
	}
</script>

<style>

</style>
