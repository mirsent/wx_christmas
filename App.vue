<script>
	export default {
		onLaunch: function () {
			console.log('App Launch')
		},
		onShow: function () {
			console.log('App Show')
		},
		onHide: function () {
			console.log('App Hide')
		}
	}
</script>

<style>
	.content{
		font-size: 42upx;
		font-weight: bold;
		padding: 40px;
		color: #FFF;
		text-align: left;
	}
	.back{
		color: rgba(255, 255, 255, .5);
		position: fixed;
		bottom: 20px;
		right: 20px;
	}
</style>
