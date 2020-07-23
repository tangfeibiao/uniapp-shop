<template>
	<view class="content">
		<view class="product-container">
			<view class="product-top">
				<swiper class="swiper" :indicator-dots="true" :autoplay="true" duration="2000">
					<swiper-item v-for="(item,index) in productInfo.imgList" :key="index">
						<image :src="item" mode="scaleToFill" class="product-img"></image>
					</swiper-item>
				</swiper>
			</view>
			<view class="product-info">
				<view class="product-info-content">
					<view class="product-name">
						{{productInfo.name}}
					</view>
					<view class="product-description">
						{{productInfo.description}}
					</view>
					<view class="product-extra-info">
						<view class="product-price" :class="{isDiscount:productInfo.isDiscount}">
							¥{{productInfo.price}}
						</view>
						<view class="product-price-discount" v-if="productInfo.isDiscount">
							¥{{productInfo.priceDiscount}}
						</view>
						<view class="product-storage">
							库存:{{productInfo.storage}}
						</view>
					</view>
				</view>
			</view>
			<view class="product-detail">
				<view class="product-specification">
					<view class="item-title">商品规格</view>
					<view class="item-content">
						<table class="table product-detail-table">
							<thead>
								<tr>
									<th>品种</th>
									<th>颜色</th>
									<th>大小</th>
									<th>价格</th>
								</tr>
							</thead>
							<tbody>
								<tr>
									<td>梨子</td>
									<td>绿色</td>
									<td>1kg/个</td>
									<td>参考上面</td>
								</tr>
								<tr>
									<td>柠檬</td>
									<td>黄色</td>
									<td>0.5kg/个</td>
									<td>参考上面</td>
								</tr>
							</tbody>
						</table>
					</view>
				</view>
				<view class="product-extra-detail">
					<view class="item-title">图文详情</view>
					<view class="item-content">
						<view class="extra-detail">
							<image src="../../static/commodity.png" mode="widthFix" class="product-detail-img"></image>
							<view class="product-detail-decription">
								又大又脆又香甜
							</view>
							<image src="../../static/501074953.png" mode="widthFix" class="product-detail-img"></image>
							<view class="product-detail-decription">
								酸酸甜甜给生活增添光彩
							</view>
						</view>
					</view>
				</view>
			</view>
			<view class="product-comment">
				<view class="item-title">商品评价</view>
				<view class="item-content">
					<view class="product-comment-list">
						<view class="comment-item" v-for='(item,index) in productInfo.commentList' :key='index'>
							<view class="comment-person">
								<view class="comment-person-detail">
									<view class="person-avatar">
										<image :src="item.avatar" mode="widthFix" class="person-avatar-img"></image>
									</view>
									<view class="person-name">
										{{item.username}}
									</view>
									<view class="person-star">
										{{item.star}}
									</view>
								</view>
								<view class="comment-time">
									{{item.datetime}}
								</view>
							</view>
							<view class="comment-content">
								{{item.comment}}
							</view>
						</view>
					</view>
				</view>
			</view>
		</view>
		<view class="bottom-item">
			<view class="buy-now">
				<view class="buy-now-text">
					立即购买
				</view>
			</view>
			<view class="add-chart">
				<view class="add-chart-text">
					加入购物车
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				productInfo: {
					userId: '1234567',
					name: '梨子和橘子',
					description: '非常好吃的梨子和橘子,不甜不要钱,大家快来买呀!',
					imgList: [
						'../../static/501074953.png',
						'../../static/commodity.png'
					],
					price: 12.5,
					priceDiscount: 9.8,
					storage: 102,
					isDiscount: true,
					commentList: [{
							username: '唐伯虎',
							avatar: '../../static/icon/my.png',
							datetime: '2019-3-14 17:11',
							star: '一颗星',
							comment: '商品非常好商品非常好商品非常好商品非常好商品非常好商品非常好'
						},
						{
							username: '唐伯虎',
							avatar: '../../static/icon/my.png',
							datetime: '2019-3-14 17:11',
							star: '二颗星',
							comment: '商品非常好商品非常好商品非常好商品非常好商品非常好商品非常好'
						},
						{
							username: '唐伯虎',
							avatar: '../../static/icon/my.png',
							datetime: '2019-3-14 17:11',
							star: '三颗星',
							comment: '商品非常好商品非常好商品非常好商品非常好商品非常好商品非常好'
						},
						{
							username: '唐伯虎',
							avatar: '../../static/icon/my.png',
							datetime: '2019-3-14 17:11',
							star: '四颗星',
							comment: '商品非常好商品非常好商品非常好商品非常好商品非常好商品非常好'
						},
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
	uni-swiper {
		height: 480rpx;
	}

	.table {
		border: 1px solid #999999;
		width: 100%;
		border-collapse: collapse;
		border-spacing: 0;
		text-align: center;

		tr {
			border: 1px solid #999999;

			th {
				border: 1px solid #999999;
			}

			td {
				border: 1px solid #999999;
				padding: 20rpx;
			}
		}
	}

	.item-title {
		font-size: 16px;
		color: #999999;
		padding: 20rpx 0;
		width: 90%;
		margin: auto;
	}

	.item-content {
		padding: 20rpx 0;
		width: 90%;
		margin: auto;
	}

	.product-top {
		height: 480rpx;

		.product-img {
			width: 100%;
		}
	}

	.product-info {
		background-color: white;

		.product-info-content {
			width: 90%;
			margin: auto;
			padding: 20rpx;

			.product-name {
				font-size: 16px;
				text-align: left;
			}

			.product-description {
				font-size: 14px;
				text-align: left;
				color: #999999;
				margin-top: 20rpx;
			}

			.product-extra-info {
				margin-top: 20rpx;
				padding-top: 20rpx;
				border-top: 1px dashed #999999;

				.product-price {
					color: red;
					font-size: 18px;
					display: inline-block;

					&.isDiscount {
						text-decoration: line-through;
						font-size: 14px;
						color: #333;
					}
				}

				.product-price-discount {
					display: inline-block;
					color: red;
					font-size: 18px;
					padding-left: 10rpx;
				}

				.product-storage {
					display: inline-block;
					float: right;
				}
			}
		}
	}

	.product-detail {
		margin-top: 20rpx;
		background-color: white;

		.product-extra-detail {
			.extra-detail {
				.product-detail-img {
					max-height: 400rpx;
					width: 100%;
				}

				.product-detail-decription {
					padding: 20rpx 0;
					color: darkblue;
				}

			}
		}
	}

	.product-comment {
		margin-top: 20rpx;
		background-color: white;

		.product-comment-list {

			.comment-item {
				padding-top: 40rpx;
				padding-bottom: 40rpx;
				border-bottom: 1px dashed  #999999;

				&:last-child {
					border-bottom: none;
				}

				.comment-person {
					margin-bottom: 10rpx;

					.comment-person-detail {

						.person-avatar {
							width: 80rpx;
							height: 80rpx;
							display: inline-block;

							.person-avatar-img {
								width: 100%;
								height: 100%;
							}
						}

						.person-name {
							display: inline-block;
							position: absolute;
							margin-top: 20rpx;
							padding-left: 30rpx;
						}

						.person-star {
							display: inline-block;
							margin-top: 20rpx;
							float: right;
						}
					}

					.comment-time {
						color: #B3B3B3;
					}
				}

				.comment-content {
					color: #B3B3B3;
				}

			}
		}
	}

	.product-container {
		position: absolute;
		height: calc(100% - 100rpx);
		width: 100%;
		overflow: auto;
	}

	.bottom-item {
		position: absolute;
		bottom: 0;
		width: 100%;
		height: 100rpx;
		background-color: white;
		border-top: 1px solid #999999;
		font-size: 22px;
		font-weight: bold;

		.buy-now {
			float: left;
			color: #1ECF8B;

			.buy-now-text {
				line-height: 100rpx;
				padding-left: 50rpx;
			}

		}

		.add-chart {
			background-color: #1ECF8B;
			width: 300rpx;
			height: 100%;
			float: right;
			display: inline-block;
			color: white;
			text-align: center;

			.add-chart-text {
				line-height: 100rpx;
			}
		}
	}
</style>
