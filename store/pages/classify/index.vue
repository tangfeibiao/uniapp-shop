<template>
	<view class="content">
		<view class="search">
			<input type="text" placeholder="搜索"/>
		</view>
		<view class="main">
			<view class="chunk">
				<view class="item-left">
					<view class="item-list" @click="MenuClick(item)" :class="MenuActive == item.id?'active': ''" v-for="(item,index) in Menu" :key="index">{{item.name}}</view>
				</view>
				<view class="item-right">
					<view class="item-block" v-for="(item,index) in commodity" :key="index">
						<image src="../../static/commodity.png" mode="widthFix"></image>
						<view class="name">{{item.name}}</view>
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
				Menu: [
					{id: 1, name: '水果'},
					{id: 2, name: '零食'},
					{id: 3, name: '蔬菜'},
					{id: 4, name: '酒饮'},
					{id: 5, name: '其他'}
				],
				MenuActive: 1,
				commodity: [
					{id:1, name: '巫山李子'},
					{id:2, name: '巫山李子'},
					{id:3, name: '巫山李子'},
					{id:4, name: '巫山李子'},
					{id:5, name: '巫山李子'},
					{id:6, name: '巫山李子'},
					{id:7, name: '巫山李子'},
					{id:8, name: '巫山李子'},
					{id:9, name: '巫山李子'},
					{id:10, name: '巫山李子'},
					{id:11, name: '巫山李子'},
					{id:12, name: '巫山李子'},
					{id:13, name: '巫山李子'},
					{id:14, name: '巫山李子'},
					{id:15, name: '巫山李子'},
				],
			}
		},
		onLoad() {
			
		},
		onShow(){
			uni.getStorageSync('MenuId')?this.MenuActive = uni.getStorageSync('MenuId'):this.MenuActive = 1;
			uni.removeStorageSync('MenuId');
		},
		methods: {
			/**
				分类切换
			**/
			MenuClick(e){
				this.MenuActive = e.id;
			},
		}
	}
</script>

<style>
page{
	background-color: #FFFFFF;
	overflow: hidden;
}
.search{
	padding: 15px;
}
.search input{
	height: 35px;
	border: 1px solid #EEEEEE;
	border-radius: 35px;
	text-align: center;
	font-size: 14px;
	color: #000000;
}
.main{
	width: 100%;
	height: calc(100% - 67px);
	position: absolute;
	top: 67px;
	left: 0px;
}
.main .chunk{
	position: relative;
	height: 100%;
}
.main .chunk .item-left{
	width: 100px;
	height: 100%;
	display: inline-block;
	position: relative;
	background-color: #F5F5F5;
	overflow: auto;
	float: left;
}
.main .chunk .item-left .item-list{
	height: 45px;
	line-height: 45px;
	text-align: center;
}
.main .chunk .item-left .item-list.active{
	background-color: #FFFFFF;
	border-top: 1px solid #F5F5F5;
	border-left: 4px solid #1ECF8B;
}
.main .chunk .item-right{
	width: calc(100% - 100px);
	height: 100%;
	display: inline-block;
	position: relative;
	overflow: auto;
	float: left;
}
.main .chunk .item-right .item-block{
	width: calc(33.33% - 13px);
	display: inline-block;
	margin-left: 10px;
	margin-bottom: 10px;
	position: relative;
}
.main .chunk .item-right .item-block image{
	width: 100%;
	border-radius: 5px;
}
.main .chunk .item-right .item-block .name{
	margin-top: 5px;
	text-align: center;
	display: -webkit-box;
	-webkit-box-orient: vertical;
	-webkit-line-clamp: 1;
	overflow: hidden;
}
</style>
