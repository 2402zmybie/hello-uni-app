<template>
	<view>
		<view>
			<text>唱歌跳舞打豆豆</text>
		</view>
		<view>
			<!-- 控制文本是否可选 -->
			<text selectable="true">唱歌跳舞打豆豆</text>
		</view>
		<view style="font-size: 30px;" space="nbsp">唱歌,跳舞 打篮球</view>
	</view>
</template>


<script>
	export default {
		data() {
			return {
				
				
			}
		},
		methods: {
			
		},
		onLoad(options) {
			console.log('上个页面传递的参数id:'+ options.id + '参数question:' + options.question)
		}
	}
</script>

<style>

</style>
