<template>
	<view>
		<view>
			<text style="font-size: 30rpx; display: flex;justify-content: center;">样式学习</text>
		</view>
		<view class="box1">
			测试文字
			<text>123</text>
		</view>
		<view class="iconfont">字体图标:&#xe639</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style lang="scss">
	@import url("./a.css");
	/* 750rpx为一整屏幕的宽度
	 rpx可以给容器设置, 也可以给文字设置
	 */
	.box1{
		width: 750rpx;
		height: 750rpx;
		// scss的使用
		background-color: $global-color;
		font-size: 20rpx;
		color: white;
		text {
			color:pink
		}
	}
</style>
