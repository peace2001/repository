<template>
	<view class="passwordWrap">
		<uni-forms>
			<uni-forms-item label="旧密码" label-align="right">
				<uni-easyinput type="password" v-model="oldPassword" placeholder="请输入旧密码"></uni-easyinput>
			</uni-forms-item>
			<uni-forms-item label="新密码" label-align="right">
				<uni-easyinput type="password" v-model="newPassword" placeholder="请输入新密码"></uni-easyinput>
			</uni-forms-item>
			<button type="primary" @click="changPwd">修改密码</button>
		</uni-forms>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				oldPassword: '',
				newPassword: ''
			}
		},
		methods: {
			changPwd() {
				if(this.oldPassword.length == 0) {
					uni.showToast({
						title: '请输入旧密码',
						icon: 'error'
					})
				} else if(this.newPassword.length == 0) {
					uni.showToast({
						title: '请输入新密码',
						icon: 'error'
					})
				} else {
					this.$request({
						url: this.$api.CHANGE_PASSWORD+'?oldPassword='+this.oldPassword+'&newPassword='+this.newPassword,
						method: 'PUT'
					}).then(res => {
						if(res.data.code == 200) {
							uni.showToast({
								title: '修改成功！'
							});
							
							this.newPassword = '';
							this.oldPassword = '';
						} else {
							uni.showToast({
								title: res.data.msg
							});
						}
					})
				}
			}
		}
	}
</script>

<style scoped>
	.passwordWrap{
		box-sizing: border-box;
		padding: 20rpx;
		margin-top: 10px;
	}
</style>
