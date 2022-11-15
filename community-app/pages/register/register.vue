<template>
	<view>
		<image style="width: 100%;" src="../../static/login/top.png"></image>
		<view class="login_bg">
			<view class="title_zh">智慧社区</view>
			<view class="title_en">Smart Community</view>
			<view class="login_bg2">
				<view class="loginWrap">
					<uni-forms ref="form" :modelValue="formData">
						<uni-forms-item label="手机号" label-align="right" required>
							<uni-easyinput type="number" v-model="formData.number" placeholder="请输入手机号" />
						</uni-forms-item>
						<uni-forms-item label="用户名" label-align="right" required>
							<uni-easyinput type="text" v-model="formData.username" placeholder="请输入用户名" />
						</uni-forms-item>
						<uni-forms-item label="密码" label-align="right" required>
							<uni-easyinput type="password" v-model="formData.password" placeholder="请输入密码" />
						</uni-forms-item>
						<uni-forms-item label="昵称" label-align="right" required>
							<uni-easyinput type="text" v-model="formData.nickname" placeholder="请输入昵称" />
						</uni-forms-item>
						<uni-forms-item label="性别" label-align="right">
							<uni-data-checkbox v-model="formData.sex" :localdata="sexs" />
						</uni-forms-item>
						<button type="primary" @click="submit">注册</button>
					</uni-forms>
					<view class="register">
						<navigator url="../login/login" hover-class="none">已有账号，立即登录</navigator>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				formData: {
					number: '',
					username: '',
					password: '',
					nickname: '',
					sex: 0
				},
				sexs: [{
					text: '男',
					value: 0
				}, {
					text: '女',
					value: 1
				}]
			}
		},
		methods: {
			submit() {
				if(this.formData.number.length != 11) {
					uni.showToast({
						title: '请输入正确手机号！',
						icon: 'error'
					})
				} else if(this.formData.username.length == 0) {
					uni.showToast({
						title: '请输入用户名！',
						icon: 'error'
					})
				} else if(this.formData.password.length == 0) {
					uni.showToast({
						title: '请输入密码！',
						icon: 'error'
					})
				} else if(this.formData.nickname.length == 0) {
					uni.showToast({
						title: '请输入昵称！',
						icon: 'error'
					})
				} else {
						uni.showToast({
							title: '注册成功！',
							icon: 'success'
						});
						
						uni.navigateTo({
							url: '../login/login'
						})
					}
						}
					
				}
			}

</script>

<style scoped>
	.login_bg{
		position: relative;
		z-index: 2;
		width: calc(100% - 30rpx);
		height: 700rpx;
		margin: -350rpx 30rpx 0 30rpx;
	}
	.title_zh,.title_en{
		margin-right: 30rpx;
		color: #fff;
		text-align: center;
		font-size: 70rpx;
		font-weight: 700;
	}
	.title_en{
		font-size: 30rpx;
	}
	.login_bg2{
		margin-top: 50rpx;
		width: calc(100% - 30rpx);
		box-sizing: border-box;
		padding: 40rpx 20rpx;
		background-color: #fff;
		border-radius: 10px;
		box-shadow: 1px 1px 2px 2px rgba(0,0,0,.1);
		overflow: hidden;
	}
	.loginWrap button{
		width: 80%;
	}
	.register{
		padding: 40rpx;
		text-align: center;
		font-size: 28rpx;
		color: #007AFF;
	}
</style>
