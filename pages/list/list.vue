<template>
	<view>
		<view>这是列表页</view>
		<view>下拉刷新</view>
		<view v-for="(item,index) in list" :key="index">{{item}}</view>
		<button @click="pullDown">触发下拉刷新</button>
		<view style="margin-top: 50rpx;">上拉加载更多</view>
		<view class="list2" v-for="(item,index) in list2">{{item}}</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list:['前端','JAVA','测试','大数据'],
				list2:['小王','小李','小美','小高','大高'],
			}
		},
		//监听页面下拉刷新
		onPullDownRefresh() {
			console.log("触发了下拉刷新")
			setTimeout(function() {
				this.list = ['测试','大数据','前端','JAVA']
				//延时两秒停止下拉刷新
				uni.stopPullDownRefresh()
			}, 2000);
		},
		//监听页面触底
		onReachBottom() {
			console.log("页面触底了")
			this.list2 = [...this.list,...['牛比的老何','小张']]
		},
		methods: {
			pullDown() {
				uni.startPullDownRefresh({
					//触发成功的回调
					success() {
						console.log("点击触发下拉刷新成功")
						setTimeout(function() {
							uni.stopPullDownRefresh()
						},1000)
					}
				})
			}
		}
	}
</script>

<style>
	.list2 {
		width: 100px;
		height: 200px;
		background: #007AFF;
		margin: 4rpx;
	}
</style>
