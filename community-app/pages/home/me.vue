<template>
	<view>
		<view class="main">
			<view class="info_bg">
				<view class="infoHead">
					<view class="title">智慧社区</view>
					<view class="infoCont">
						<image src="../../static/me/touxiang.jpg"></image>
						<view class="userName">
							<uni-icons size="28" color="#fff" type="person-filled"></uni-icons>
							<text>gxx</text>
						</view>
					</view>
				</view>
			</view>
		</view>
		<view>
			<uni-list>
				<uni-list-item @click.native="goto('../myinfo/myinfo')" title="个人信息" showArrow></uni-list-item>
				<uni-list-item @click.native="goto('../changePwd/changePwd')" title="修改密码" showArrow></uni-list-item>
				<uni-list-item @click.native="goto('../feedback/feedback')" title="意见反馈" showArrow></uni-list-item>
				<uni-list-item title="关于" showArrow></uni-list-item>
			</uni-list>
		</view>
		<view class="logOut">
			<button @click="login_out()" type="primary" >退出登录</button>
		</view>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				
			}
		},
		methods:{
			login_out(){
				uni.navigateTo({
					url:'/pages/login/login'
				})
				uni.clearStorage()
			},
			goto(url) {
				uni.navigateTo({
					url: url
				})
			}
		}
	}
	
</script>

<style>
	.info_bg{
		width: calc(100% - 60rpx);
		box-sizing: border-box;
		padding: 30rpx;
		background: url(../../static/login/top.png) no-repeat;
		background-color: #fff;
		margin: 30rpx auto;
		border-radius: 15rpx;
		box-shadow: 2px 2px 2px 2px rgba(0,0,0,.1);
	}
	.infoHead image{
		width: 180rpx;
		height: 180rpx;
		border-radius: 50%;
	}
	.title{
		font-size: 32rpx;
		font-weight: 700;
		color: #fff;
	}
	.userName{
		font-size: 48rpx;
		color: #fff;
		margin-left: 10rpx;
	}
	.infoCont{
		display: flex;
		align-items: center;
		padding-top: 20rpx;
	}
</style>
