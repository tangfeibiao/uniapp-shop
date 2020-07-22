<template>
	<view class="content">
		<view class="my-header">
			<view class="my-profile">
				<view class="profile">
					<view class="profile-img">
						<image src="../../static/icon/my.png" class="profile-img-item"></image>
					</view>
					<view class="profile-content">
						<view class="profile-title">
							{{userInfo.nickName}}
						</view>
						<view class="profile-mobile">
							{{userInfo.mobile}}
						</view>
					</view>
					<view class="profile-daily-check">
						<view class="daily-check-button">
							马上签到
						</view>
					</view>
				</view>
				<view class="profile-extra">
					<view class="profile-extra-list">
						<view class="profile-extra-item">
							<view class="profile-extra-item-number">
								23
							</view>
							<view class="profile-extra-item-name">
								历史
							</view>
						</view>
						<view class="profile-extra-item">
							<view class="profile-extra-item-number">
								14
							</view>
							<view class="profile-extra-item-name">
								收藏
							</view>
						</view>
						<view class="profile-extra-item">
							<view class="profile-extra-item-number">
								56
							</view>
							<view class="profile-extra-item-name">
								关注
							</view>
						</view>
						<view class="profile-extra-item">
							<view class="profile-extra-item-number">
								27
							</view>
							<view class="profile-extra-item-name">
								优惠卷
							</view>
						</view>
					</view>
				</view>
			</view>
			<view class="my-order">
				<view class="my-order-title">
					<view class="title-name">
						全部订单
					</view>
					<image src="../../static/icon/right-array.png" class="title-icon"></image>
				</view>
				<view class="my-order-content">
					<view class="order-item-list">
						<view class="order-item">
							<image src="../../static/icon/purch.png" class="order-item-icon"></image>
							<view class="order-item-name">
								待付款
							</view>
						</view>
						<view class="order-item">
							<image src="../../static/icon/packin.png" class="order-item-icon"></image>
							<view class="order-item-name">
								待发货
							</view>
						</view>
						<view class="order-item">
							<image src="../../static/icon/shipping.png" class="order-item-icon"></image>
							<view class="order-item-name">
								待收货
							</view>
						</view>
						<view class="order-item">
							<image src="../../static/icon/comment.png" class="order-item-icon"></image>
							<view class="order-item-name">
								评价
							</view>
						</view>
						<view class="order-item">
							<image src="../../static/icon/withdraw.png" class="order-item-icon"></image>
							<view class="order-item-name">
								退款/售后
							</view>
						</view>
					</view>
				</view>
			</view>
		</view>
		<view class="my-content">
			<view class="my-item-list">
				<view class="my-item">
					<view class="my-item-left">
						<image src="../../static/icon/daily.png" class="my-item-icon"></image>
					</view>
					<view class="my-item-name">
						每日签到
					</view>
					<view class="my-item-decription">
						<view class="item-decription-name">
							今日签到
						</view>
						<view class="item-decription-icon">
							<image src="../../static/icon/right-array.png" class="title-icon"></image>
						</view>
					</view>
				</view>
				<view class="my-item">
					<view class="my-item-left">
						<image src="../../static/icon/withdraw.png" class="my-item-icon"></image>
					</view>
					<view class="my-item-name">
						每日返现
					</view>
					<view class="my-item-decription">
						<view class="item-decription-name">
							去签到
						</view>
						<view class="item-decription-icon">
							<image src="../../static/icon/right-array.png" class="title-icon"></image>
						</view>
					</view>
				</view>
				<view class="my-item">
					<view class="my-item-left">
						<image src="../../static/icon/invite.png" class="my-item-icon"></image>
					</view>
					<view class="my-item-name">
						邀请有礼
					</view>
					<view class="my-item-decription">
						<view class="item-decription-name">
							可得100元现金
						</view>
						<view class="item-decription-icon">
							<image src="../../static/icon/right-array.png" class="title-icon"></image>
						</view>
					</view>
				</view>
				<view class="my-item">
					<view class="my-item-left">
						<image src="../../static/icon/my-group.png" class="my-item-icon"></image>
					</view>
					<view class="my-item-name">
						我的拼团
					</view>
					<view class="my-item-decription">
						<view class="item-decription-name">
						</view>
						<view class="item-decription-icon">
							<image src="../../static/icon/right-array.png" class="title-icon"></image>
						</view>
					</view>
				</view>
				<view class="my-item">
					<view class="my-item-left">
						<image src="../../static/icon/settings.png" class="my-item-icon"></image>
					</view>
					<view class="my-item-name">
						设置
					</view>
					<view class="my-item-decription">
						<view class="item-decription-name">
						</view>
						<view class="item-decription-icon">
							<image src="../../static/icon/right-array.png" class="title-icon"></image>
						</view>
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
				userInfo: {
					userId: '1234567',
					name: 'tangfeibiao',
					nickName: '吃货的世界',
					avatar: '',
					mobile: '13212343234',
					collect: 14, //收藏
					focus: 56, //关注
					coupon: 27, //优惠卷
					history: 23, //历史记录
					isDailyCheckIn: false, //是否签到
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
	.my-header {
		background-color: rgb(30, 207, 139);
		height: 400rpx;
		color: white;
		font-family: 'Microsoft Yahei';

		.my-profile {
			height: 400rpx;
			display: block;

			.profile {
				display: block;
				height: 100rpx;
				padding-top: 30rpx;
				padding-bottom: 30rpx;
				width: 90%;
				margin: auto;

				.profile-img {
					width: 100rpx;
					height: 100rpx;
					border-radius: 100rpx;
					background-color: white;
					margin-left: 20rpx;
					display: inline-block;

					.profile-img-item {
						width: 100%;
						height: 100%;
					}
				}

				.profile-content {
					height: 50rpx;
					color: white;

					padding-left: 20rpx;
					font-size: 16px;
					font-weight: bold;
					display: inline-block;

					.profile-mobile {
						padding-top: 10rpx;
					}
				}

				.profile-daily-check {
					width: 170rpx;
					height: 80rpx;
					float: right;
					padding-right: 20rpx;
					padding-top: 20rpx;

					.daily-check-button {
						border: 1px solid white;
						color: white;
						padding: 15rpx 25rpx;
						border-radius: 30rpx;
					}
				}

			}

			.profile-extra {
				height: 150rpx;
				margin-top: 20rpx;

				.profile-extra-list {
					width: 90%;
					margin: auto;
					display: flex;
					flex-direction: row;
					text-align: center;
					font-size: 16px;

					.profile-extra-item {
						flex: 1;

						.profile-extra-item-number {
							font-weight: bold;
						}

					}
				}
			}
		}

		.my-order {
			position: relative;
			height: 250rpx;
			width: 90%;
			margin: auto;
			border-radius: 20rpx;
			background-color: white;
			top: -100rpx;
			color: black;

			.my-order-title {
				height: 100rpx;

				.title-name {
					font-size: 14px;
					padding-top: 20rpx;
					padding-left: 20rpx;
				}

			}

			.my-order-content {
				height: calc(100% - 100rpx);

				.order-item-list {
					width: 95%;
					margin: auto;
					display: flex;
					flex-direction: row;
					text-align: center;
					font-size: 16px;

					.order-item {
						flex: 1;

						.order-item-icon {
							width: 50rpx;
							height: 50rpx;
						}

						.order-item-name {
							font-size: 14px;
							margin-top: 20rpx;
						}
					}
				}
			}

		}
	}

	.my-content {
		background-color: #F6F6F6;
		margin-top: 180rpx;

		.my-item-list {
			background-color: white;

			.my-item {
				height: 100rpx;
				border-bottom: 1px solid #F6F6F6;
				display: flex;
				line-height: 100rpx;
				width: 90%;
				margin: auto;

				.my-item-left {
					widows: 10%;

					.my-item-icon {
						width: 50rpx;
						height: 50rpx;
						padding-left: 20rpx;
						vertical-align: middle;
						display: inline-block;
					}
				}

				.my-item-name {
					width: 40%;
					padding-left: 40rpx;
					font-size: 18px;
					display: inline-block;
				}

				.my-item-decription {
					width: 50%;
					text-align: right;
					display: inline-block;

					.item-decription-name {
						color: rgba(0, 0, 0, 0.6);
						font-size: 16px;
						padding-right: 40rpx;
						display: inline-block;
					}

					.item-decription-icon {
						display: inline-block;
						float: right;

						.title-icon {
							position: inherit;
						}
					}
				}
			}
		}
	}

	.title-icon {
		width: 20rpx;
		height: 30rpx;
		position: absolute;
		right: 20rpx;
		top: 20rpx;
	}
</style>
