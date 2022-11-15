<script>
	export default {
		onLaunch: function() {
			console.warn('当前组件仅支持 uni_modules 目录结构 ，请升级 HBuilderX 到 3.1.0 版本以上！')
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
	/* 隐藏指定页面的返回按钮 */
	uni-page[data-page="pages/login/login"] .uni-page-head-hd {
		display: none;
	}
	.df {
		display: flex;
	}
	.wbg {
		background: #FFFFFF;
		border-radius: 20rpx;
		margin: 20rpx;
		padding: 20rpx;
		box-shadow: 2rpx 2rpx 5rpx 2rpx #CCCCCC;
	}
	.tips{
		font-size: 30rpx;
		font-weight: 700;
	}
	.btn{
		background-color: #6CB6FF;
		color: white;
		font-size: 28rpx;
	}
	.ml20 {
		margin-left: 20rpx;
	}
	
	.mr20 {
		margin-right: 20rpx;
	}
	
	.mt20 {
		margin-top: 20rpx;
	}
	
	.mb20 {
		margin-bottom: 20rpx;
	}
	.ml10 {
		margin-left: 10rpx;
	}
	
	.mr10 {
		margin-right: 10rpx;
	}
	
	.mt10 {
		margin-top: 10rpx;
	}
	
	.mb10 {
		margin-bottom: 10rpx;
	}
	.m20 {
		margin: 20rpx;
	}
	
	.p20 {
		padding: 20rpx;
	}
	.pl20 {
		padding-left: 20rpx;
	}
	.pt20 {
		padding-top: 20rpx;
	}
	.pb20 {
		padding-bottom: 20rpx;
	}
	.pr20 {
		padding-right: 20rpx;
	}
	.w100{
		width: 100%;
	}
	.h100{
		height: 100%;
	}
	.alginleft{
		align-items: flex-start;
	}
	.alginright{
		align-items: flex-end;
	}
	.algincenter{
		align-items: center;
	}
	.justifyleft{
		justify-content: flex-start;
	}
	.justifyright{
		justify-content: flex-end;
	}
	.justifycenter{
		justify-content: center;
	}
	.fw700{
		font-weight: 700;
	}
	.white{
		color: white;
	}
</style>
