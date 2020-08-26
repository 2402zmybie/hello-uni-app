<template>
	<view>
		<view>{{ num }}</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				num:0
			};
		},
		created() {
			//在另一个页面注册全局事件
			uni.$on('updateNum',(num) => {
				this.num += num
			})
		}
	}
</script>

<style>

</style>
