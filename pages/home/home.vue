<template>
	<view>
		<view>数据绑定的学习</view>
		<view>{{ msg }}</view>
		<view>{{ "你好" + num }}</view>
		<view>{{ 1 + 1 }}</view>
		<view>{{ flag?"我是真的":"我是假的" }}</view>
		<image :src="imageUrl"></imaeg>
		<view v-for="(item,index) in arr" :key="item.id">序号:{{item.id}}, 名字:{{ item.name }}, 年龄:{{ item.age }}</view>
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
			
		}
	}
</script>

<style>

</style>
