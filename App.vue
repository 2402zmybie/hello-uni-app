<script>
	export default {
		// 退出重新启动app,会触发声明周期函数
		onLaunch: function() {
			console.log('App Launch')
		},
		onShow: function() {
			//每次进入app,即会触发
			console.log('App Show')
		},
		onHide: function() {
			//app不见了,即会触发
			console.log('App Hide')
		},
		onError: (err) => {
			console.log(err)
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
