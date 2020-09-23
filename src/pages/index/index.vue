<template>
	<view>
		<navTop :title="navTop.title" :showBack='false' :bgColor='navTop.bgColor'></navTop>
		<image mode="aspectFill" :src="src" class="header-img"></image>
		<view class="content">
			<view class="search-contain">
				<input class="uni-input" focus placeholder="自动获得焦点" />
				<view>上海</view>
			</view>
		</view>
	</view>
</template>

<script>
	import navTop from '@/components/navTop.vue'

	export default {

		components: {
			navTop
		},

		data() {
			return {
				navTop: {
					title: '趣练鹰',
					bgColor: '#ffaaaa'
				},
				src: '../../static/index/background.png',

			}
		},

		onLoad() {

		},

		methods: {

		}
	}
</script>

<style>
	.header-img {
		width: 750rpx;
		height: 423rpx;
		display: block;
	}

	.content {
		width: 750rpx;
		border: 1rpx solid red;
		position: absolute;
		top: 158rpx;
	}
</style>
