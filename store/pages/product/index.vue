<template>
	<view class="content">
		<view class="product-top">
			<swiper class="swiper" :indicator-dots="true" :autoplay="true" duration="2000">
				<swiper-item v-for="(item,index) in productInfo.imgList" :key="index">
					<image :src="item" mode="scaleToFill" class="product-img"></image>
				</swiper-item>
			</swiper>
		</view>
		<view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				productInfo: {
					userId: '1234567',
					name: '梨子',
					imgList: [
						'../../static/501074953.png',
						'../../static/commodity.png'
					]
				}
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style lang='scss' scoped>
	.product-top {
		height: 500rpx;
	}

	.product-img {
		width: 100%;
	}

	uni-swiper {
		height: 480rpx;
	}
</style>
