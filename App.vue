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

<style>
	/*每个页面公共css */
.text-overflow{
	/* 限制文字长度 */
	overflow: hidden;
	text-overflow: ellipsis;
	white-space: nowrap;
}
</style>
