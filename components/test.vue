<template>
	<view>
		<view id="myView">
			这是一个test组件{{num}}
		</view>
		<view>父组件传给子组件的数据{{ title }}</view>
		<button @click="sendNum">给父组件传值</button>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				num:3,
				timer:null
			};
		},
		props:['title'],
		methods:{
			//给父组件传值要使用事件触发的方式
			sendNum() {
				this.$emit('myEvent',this.num)
			}
		},
		//组件生命周期, 数据没有渲染
		beforeCreate() {
			console.log('实例已经开始初始化了')
			console.log(this.num)  //undefined
		},
		//作用: 初始化数据
		created() {
			console.log('created:'+  this.num)
			this.timer = setInterval(()=> {
				console.log("定时器开启")
			},1000)
		},
		//H5才有document, 数据更新之之前调用
		beforeMount() {
			console.log('beforeMount',document.getElementById('myView'))
		},
		//H5才有document, 作用: 操作DOM
		mounted() {
			console.log('mount',document.getElementById('myView'))
		},
	
		//组件销毁的时候的回调. 作用: 清除定时器等
		destroyed() {
			console.log('组件销毁了')
			clearInterval(this.timer)
		}
		
	}
</script>

<style>

</style>
