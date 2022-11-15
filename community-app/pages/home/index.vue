<template>
	<view class="container">
		<view>
		<swiper class="swiper" circular :indicator-dots="true" :autoplay="true" :interval="3000"
			:duration="1000">
			<swiper-item >
				<image src="../../static/bg1.png"></image>
			</swiper-item>
			<swiper-item >
				<image src="../../static/bg1.png"></image>
			</swiper-item>
			<swiper-item >
				<image src="../../static/bg1.png"></image>
			</swiper-item>
		</swiper>
		</view>
		<view class="grid-box">
			<uni-grid :column="4" border-color="#03a9f4" @change="change" >
				<uni-grid-item @click.native="goto('../history/history')">
					<view class="grid-item-box">
						<image class="image" src="../../static/icon/rili.png" mode="aspectFill" />
					</view>
				</uni-grid-item>
				<uni-grid-item :index="1">
					<view class="grid-item-box">
						<image class="image" src="../../static/icon/women.png" mode="aspectFill" />
					</view>
				</uni-grid-item>
				<uni-grid-item :index="2">
					<view class="grid-item-box">
						<image class="image" src="../../static/icon/dingwei.png" mode="aspectFill" />
					</view>
				</uni-grid-item>
				<uni-grid-item :index="3">
					<view class="grid-item-box">
						<image class="image" src="../../static/icon/shanchu.png" mode="aspectFill" />
					</view>
				</uni-grid-item>
				<uni-grid-item :index="4">
					<view class="grid-item-box">
						<image class="image" src="../../static/icon/pingtai.png" mode="aspectFill" />
					</view>
				</uni-grid-item>
			</uni-grid>
		</view>
		
	</view>
</template>

<script>
	export default{
		data(){
			return{
				item:{
					index:''
				}
			}
		},
		methods:{
			goto(url) {
				uni.navigateTo({
					url: url
				})
			}
		},
	}
	
</script>

<style>
	.container {
		padding: 10px;
	}
	.grid-item-box {
			flex: 1;
			// position: relative;
			/* #ifndef APP-NVUE */
			display: flex;
			/* #endif */
			flex-direction: column;
			align-items: center;
			justify-content: center;
			padding: 15px 0;
		}
		.grid-box{
			padding-top: 30rpx;
		}
	
		.grid-item-box-row {
			flex: 1;
			// position: relative;
			/* #ifndef APP-NVUE */
			display: flex;
			/* #endif */
			flex-direction: row;
			align-items: center;
			justify-content: center;
			padding: 15px 0;
		}
		.image {
			width: 50px;
			height: 50px;
		}
		.swiper{
			width: 100%;
			height: 155px;
			border-radius: 10px;
			overflow: hidden;
		}
		.swiper image{
			width: 100%;
			height: 155px;
		}
</style>
