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
	@import 'utils/css/for.scss';
	@import 'utils/css/index.scss';
	@import "@/uni_modules/uview-ui/index.scss";
	page {	
		background: #F7F7F7;
	}
</style>
