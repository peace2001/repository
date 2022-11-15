<template>
	<view>
		<uni-forms  :modelValue="formData">
			<uni-forms-item label="账号" required>
				<uni-easyinput v-model="formData.username" placeholder="请输入账号" />
			</uni-forms-item>
			<uni-forms-item label="密码" required>
				<uni-easyinput v-model="formData.password" placeholder="请输入密码" />
			</uni-forms-item>
			<button @click="login" type="primary">登录</button>
		</uni-forms>
		<view class="register">
			<navigator url="../register/register" hover-class="none">立即注册</navigator>
		</view>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				formData:{
					username:'',
					password:''
				}
			}
		},
		methods:{
			login(){
				if(this.formData.username.length == 0) {
					uni.showToast({
						title: '请先输入账号！',
						icon: 'error'
					})
				} else if(this.formData.password.length == 0) {
					uni.showToast({
						title: '请先输入密码！',
						icon: 'error'
					})
				} else{
					uni.switchTab({
						url:'../home/index'
					})
				}
			}
		}
	}
</script>

<style>
	.register{
		padding: 40rpx;
		text-align: right;
		font-size: 28rpx;
		color: #007AFF;
	}
</style>
