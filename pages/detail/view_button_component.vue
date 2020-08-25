<template>
	<!-- 类似于html的div -->
	<view>
		<view class="box2" hover-class="box2-active">
			<!-- 属性hover-stop-propagation阻止父布局出现点击事件 -->
			<view class="box" hover-class="box-active" :hover-start-time="2000" :hover-stay-time="2000" hover-stop-propagation="true">
				我是一个大盒子
			</view>
		</view>
		<button>按钮</button>
		<button size="mini">按钮</button>
		<button size="mini" type="primary">按钮</button>
		<button type="primary" plain="true">按钮</button>
		<button type="primary" disabled="true">按钮</button>
		<button type="primary" loading="true"></button>
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

<style>
	.box{
		width: 100px;
		height: 100px;
		background: #007AFF;
	}
	.box-active {
		width: 100px;
		height: 100px;
		background: #f00;
	}
	.box2 {
		width: 200px;
		height: 200px;
		background: blue;
	}
	.box2-active {
		background: pink;
	}
</style>
