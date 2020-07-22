<template>
	<view class="content">
		<view class="roof">
			<view class="banner">
				<image src="../../static/banner.png" mode="widthFix"></image>
			</view>
			<view class="menu">
				<view class="ly-20" @click="MenuClick(1)">
					<view class="icon icon1">
						<image src="../../static/menu/menu1.png"></image>
					</view>
					<view class="name">水果</view>
				</view>
				<view class="ly-20" @click="MenuClick(2)">
					<view class="icon icon2">
						<image src="../../static/menu/menu2.png"></image>
					</view>
					<view class="name">零食</view>
				</view>
				<view class="ly-20" @click="MenuClick(3)">
					<view class="icon icon3">
						<image src="../../static/menu/menu3.png"></image>
					</view>
					<view class="name">蔬菜</view>
				</view>
				<view class="ly-20" @click="MenuClick(4)">
					<view class="icon icon4">
						<image src="../../static/menu/menu4.png"></image>
					</view>
					<view class="name">酒饮</view>
				</view>
				<view class="ly-20" @click="MenuClick(5)">
					<view class="icon icon5">
						<image src="../../static/menu/menu5.png"></image>
					</view>
					<view class="name">其他</view>
				</view>
			</view>
		</view>
		<view class="recommend">
			<view class="recommend-menu">
				<scroll-view class="scroll-view_H" scroll-x="true">
					<view id="demo1" class="scroll-view-item_H" @click="recommendMenuClick(item)" :class="recommendMenuActive == item.id?'active': ''"
					 v-for="(item,index) in recommendMenu" :key="index">{{item.name}}</view>
				</scroll-view>
			</view>
		</view>
		<view class="item">
			<view class="item-block" v-for="(item,index) in commodity" :key="index" @click="productDetail(item.id)">
				<image src="../../static/commodity.png" mode="widthFix"></image>
				<view class="name">{{item.name}}</view>
				<view class="price">￥<text>{{item.price}}</text></view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				recommendMenu: [{
						id: 1,
						name: '推荐'
					},
					{
						id: 2,
						name: '水果'
					},
					{
						id: 3,
						name: '肉蛋'
					},
					{
						id: 4,
						name: '零食'
					},
					{
						id: 5,
						name: '乳品'
					},
					{
						id: 6,
						name: '粮油'
					},
					{
						id: 7,
						name: '水果'
					},
					{
						id: 8,
						name: '肉蛋'
					},
					{
						id: 9,
						name: '零食'
					},
					{
						id: 10,
						name: '乳品'
					},
					{
						id: 11,
						name: '粮油'
					}
				],
				recommendMenuActive: 1,
				commodity: [{
						id: 1,
						name: '巫山二级李子 1.25kg/盒(约40-43颗)',
						price: '22.00'
					},
					{
						id: 2,
						name: '巫山二级李子 1.25kg/盒(约40-43颗)',
						price: '22.00'
					},
					{
						id: 3,
						name: '巫山二级李子 1.25kg/盒(约40-43颗)',
						price: '22.00'
					},
					{
						id: 4,
						name: '巫山二级李子 1.25kg/盒(约40-43颗)',
						price: '22.00'
					},
					{
						id: 5,
						name: '巫山二级李子 1.25kg/盒(约40-43颗)',
						price: '22.00'
					},
					{
						id: 6,
						name: '巫山二级李子 1.25kg/盒(约40-43颗)',
						price: '22.00'
					},
					{
						id: 7,
						name: '巫山二级李子 1.25kg/盒(约40-43颗)',
						price: '22.00'
					},
					{
						id: 8,
						name: '巫山二级李子 1.25kg/盒(约40-43颗)',
						price: '22.00'
					},
					{
						id: 9,
						name: '巫山二级李子 1.25kg/盒(约40-43颗)',
						price: '22.00'
					},
					{
						id: 10,
						name: '巫山二级李子 1.25kg/盒(约40-43颗)',
						price: '22.00'
					},
				],
			}
		},
		onLoad() {

		},
		methods: {
			/**
				滑动切换
			**/
			recommendMenuClick(e) {
				this.recommendMenuActive = e.id;
			},

			/**
				菜单切换
			**/
			MenuClick(e) {
				uni.setStorageSync('MenuId', e);
				uni.switchTab({
					url: '/pages/classify/index'
				});
			},

			productDetail(id) {
				uni.navigateTo({
					url: '/pages/product/index?productId=' + id
				});
			}
		}
	}
</script>

<style>
	.roof {
		background-color: #FFFFFF;
		padding-bottom: 10px;
		position: relative;
	}

	.roof .banner {
		padding: 10px 10px;
		position: relative;
	}

	.roof .banner image {
		width: 100%;
		height: 100%;
		border-radius: 8px;
	}

	.roof .menu {
		position: relative;
	}

	.roof .menu .ly-20 {
		width: 20%;
		display: inline-block;
		text-align: center;
		position: relative;
	}

	.roof .menu .ly-20 .icon {
		width: 45px;
		height: 45px;
		margin: 0 auto;
		border-radius: 50%;
		text-align: center;
		position: relative;
		margin-bottom: 5px;
	}

	.roof .menu .ly-20 .icon.icon1 {
		background-color: #F6CA47;
	}

	.roof .menu .ly-20 .icon.icon2 {
		background-color: #72A2F3;
	}

	.roof .menu .ly-20 .icon.icon3 {
		background-color: #FC544B;
	}

	.roof .menu .ly-20 .icon.icon4 {
		background-color: #12C989;
	}

	.roof .menu .ly-20 .icon.icon5 {
		background-color: #1DCEE0;
	}

	.roof .menu .ly-20 .icon image {
		width: 30px;
		height: 30px;
		margin-top: 7.5px;
	}

	.recommend {
		background-color: #FFFFFF;
		padding: 10px 0px 5px 0px;
		margin-top: 10px;
		font-size: 16px;
		position: relative;
		border-bottom: 1px solid #F5F5F5;
	}

	.recommend .recommend-menu {
		margin-right: 10px;
	}

	.recommend .recommend-menu .scroll-view_H {
		white-space: nowrap;
		width: 100%;
	}

	.recommend .recommend-menu .scroll-view-item_H {
		display: inline-block;
		margin: 0 10px;
	}

	.recommend .recommend-menu .scroll-view-item_H.active {
		color: #1ECF8B;
		border-bottom: 1px solid #1ECF8B;
		padding-bottom: 5px;
	}

	.item {
		background-color: #FFFFFF;
		padding: 0 10px;
		position: relative;
	}

	.item .item-block {
		width: calc(50% - 5px);
		display: inline-block;
		position: relative;
		margin-top: 10px;
	}

	.item .item-block:nth-child(2n) {
		margin-left: 10px;
	}

	.item .item-block image {
		width: 100%;
		border-radius: 8px;
	}

	.item .item-block .name {
		margin-top: 5px;
		display: -webkit-box;
		-webkit-box-orient: vertical;
		-webkit-line-clamp: 2;
		overflow: hidden;
	}

	.item .item-block .price {
		margin-top: 5px;
		color: #EA2A39;
	}

	.item .item-block .price text {
		font-size: 18px;
	}
</style>
