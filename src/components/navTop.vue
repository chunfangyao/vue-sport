<template>
	<view>
		<view class="top-header">
			<view class="header">
				<block v-if="firstPage">
					<image v-if="showBack" @click="navBack" class="is-share" src="../static/public/is-home.png" />
				</block>
				<block v-else>
					<image v-if="showBack" @click="navBack" class="img" src="../static/public/back-icon.png" mode="left" />
				</block>
				<view></view>

				<view class="title"></view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name: 'navTop',
		props: {
			title: {
				type: String,
				default: "标题"
			},
			showBack: {
				type: Boolean,
				default: true
			},
			bgColor: {
				type: String,
				default: "#FFFFFF00"
			}
		},

		data() {
			return {
				paddingTopNum: uni.getSystemInfoSync().statusBarHeight,
				isIos: uni.getSystemInfoSync().system.indexOf('ios') > -1 ? 44 : 48,
				firstPage: false
			};
		},

		methods: {
			navBack: function() {
				if (getCurrentPages().length == 1) {
					uni.switchTab({
						url: '/pages/index/index',
					})
				} else {
					uni.navigateBack({
						delta: 1
					})
				}
			},
		}
	}
</script>

<style>
	.top-header {
		position: fixed;
		height: 68rpx;
		line-height: 68rpx;
		background: #fff;
		top: 0;
		left: 0;
		background-color: rgba(255, 255, 255, 0);
		display: flex;
		color: rgba(255, 255, 255, 1);
		align-items: center;
		z-index: 10;
		width: 100%;
	}

	.header {
		width: 437rpx;
		display: flex;
		justify-content: space-between;
		align-items: center;
		margin-top: -8rpx
	}

	.header .img {
		width: 50rpx;
		height: 35rpx;
		margin-left: 20rpx;
	}

	.is-share {
		width: 40rpx;
		height: 40rpx;
		margin-left: 20rpx;
	}

	.title {
		width: 128rpx;
		height: 45rpx;
		font-size: 32rpx;
		font-family: PingFangSC-Medium, PingFang SC;
		font-weight: 500;
		color: rgba(255, 255, 255, 1);
		line-height: 45rpx;
	}
</style>
