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
				console.log("点击列表: " + index)
			}
			
		},
		// 页面的生命周期
		onLoad(options) {
			// 监听页面加载，其参数为上个页面传递的数据，参数类型为Object（用于页面传参）[不会多次触发]
			console.log("页面加载" + options)
		},
		//监听页面显示。页面每次出现在屏幕上都触发，包括从下级页面点返回露出当前页面[可触发多次]
		onShow() {
			console.log("页面显示了")
		},
		onReady() {
			//监听页面初次渲染完成[不会触发多次]
			console.log("监听页面初次渲染完成")
		},
		onHide() {
			//[触发多次]
			console.log("监听页面隐藏")
		}
	}
</script>

<style>

</style>
