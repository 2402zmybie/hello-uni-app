<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style lang="scss">
	/*每个页面公共css */
	/* 这个是全部的样式,定义在局部的样式会把全局的覆盖掉
	.box1 {
		background: pink;
	} */
	/* 在公共样式引入字体图标 */
	@import url("./static/fonts/iconfont.css");
</style>
