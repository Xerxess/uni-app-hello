<template>
	<view>
		<swiper class="swiper" indicator-dots="true">
			<swiper-item class="swiper__back1"></swiper-item>
			<swiper-item class="swiper__back2"></swiper-item>
			<swiper-item class="swiper__back3"></swiper-item>
			<swiper-item class="swiper__back4">
				<button class="go-home" @click="goHome"> 进入主页 </button>
			</swiper-item>
		</swiper>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			};
		},
		methods: {
			goHome() {
				uni.switchTab({
					url:'/pages/tabBar/component/component'
				})
				plus.navigator.setFullscreen(false);
			}
		},
	}
</script>

<style lang="scss">
	.swiper {
		height: 100%;
		width: 100%;
		position: fixed;
		top:0;
		left:0;
		z-index: 9999;
	}

	swiper-item {
		position: relative;
	}

	.swiper__back1 {
		background: url(~@/static/app-plus/guide/1.jpg) no-repeat center;
		background-size: 100% 100%;
	}
	
	.swiper__back2 {
		background: url(~@/static/app-plus/guide/2.jpg) no-repeat center;
		background-size: 100% 100%;
	}
	
	.swiper__back3 {
		background: url(~@/static/app-plus/guide/3.jpg) no-repeat center;
		background-size: 100% 100%;
	}
	.swiper__back4 {
		background: url(~@/static/app-plus/guide/4.jpg) no-repeat center;
		background-size: 100% 100%;
	}

	.go-home {
		position: absolute;
		right:10%;
		bottom:10%;
	}
</style>
