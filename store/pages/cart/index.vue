<template>
	<view class="content">
		<view class="item">
			<view class="item-list" v-for="(item,index) in cartList" :key="index" v-if="item.number > 0">
				<view class="select" :class="item.active == true?'active':''"></view>
				<view class="item-text">
					<view class="item-image"><image src="../../static/commodity.png" mode="widthFix"></image></view>
					<view class="item-chunk">
						<view class="name">{{item.name}}</view>
						<view class="chunk">
							<text class="price">￥<text>{{item.price}}</text></text>
							<view class="count">
								<view class="jian">-</view>
								<view class="number">{{item.number}}</view>
								<view class="jia">+</view>
							</view>
						</view>
					</view>
				</view>
			</view>
		</view>
		<view class="bar">
			<view class="select"></view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				cartList: [
					{id: 1, name: '巫山二级李子 1.25kg/盒(约40-43颗)', price: '22.00', number: 1, active: false},
					{id: 2, name: '巫山二级李子 1.25kg/盒(约40-43颗)', price: '22.00', number: 1, active: false},
					{id: 3, name: '巫山二级李子 1.25kg/盒(约40-43颗)', price: '22.00', number: 1, active: false},
					{id: 4, name: '巫山二级李子 1.25kg/盒(约40-43颗)', price: '22.00', number: 1, active: false},
					{id: 5, name: '巫山二级李子 1.25kg/盒(约40-43颗)', price: '22.00', number: 1, active: false}
				]
			}
		},
		onLoad() {

		},
		methods: {
			
		}
	}
</script>

<style>
page{
	overflow: hidden;
}
.item{
	position: absolute;
	height: calc(100% - 50px);
	overflow: auto;
}
.item-list{
	background-color: #FFFFFF;
	margin-top: 10px;
	position: relative;
	padding: 10px 10px;
}
.item-list:last-child{
	margin-bottom: 10px;
}
.item-list .select{
	width: 17px;
	height: 17px;
	border-radius: 50%;
	border: 1px solid #EEEEEE;
	position: absolute;
	top: 50%;
	margin-top: -8.5px;
}
.item-list .select.active{
	background-image: url(../../static/select.png);
	background-size: 100% 100%;
	border: 0;
}
.item-list .item-text{
	padding-left: 32px;
	position: relative;
	height: 100px;
}
.item-list .item-text .item-image{
	width: 100px;
	height: 100px;
	position: absolute;
	top: 0px;
}
.item-list .item-text .item-image image{
	width: 100%;
	border-radius: 5px;
}
.item-list .item-text .item-chunk{
	height: 100%;
	padding-left: 110px;
	position: relative;
}
.item-list .item-text .item-chunk .name{
	display: -webkit-box;
	-webkit-box-orient: vertical;
	-webkit-line-clamp: 3;
	overflow: hidden;
}
.item-list .item-text .item-chunk .chunk{
	position: absolute;
	bottom: 0px;
	width: calc(100% - 110px);
}
.item-list .item-text .item-chunk .chunk .price{
	color: #EA2A39;
}
.item-list .item-text .item-chunk .chunk .price text{
	font-size: 18px;
}
.item-list .item-text .item-chunk .chunk .count{
	display: inline-block;
	float: right;
}
.item-list .item-text .item-chunk .chunk .count view{
	display: inline-block;
}
.item-list .item-text .item-chunk .chunk .count .jian{
	width: 25px;
	height: 20px;
	border:1px solid #EEEEEE;
	text-align: center;
	line-height: 20px;
	border-radius: 10px 0 0 10px;
}
.item-list .item-text .item-chunk .chunk .count .jia{
	width: 25px;
	height: 20px;
	border:1px solid #EEEEEE;
	text-align: center;
	line-height: 20px;
	border-radius: 0 10px 10px 0;
}
.item-list .item-text .item-chunk .chunk .count .number{
	width: 30px;
	height: 20px;
	text-align: center;
	line-height: 20px;
	border:1px solid #EEEEEE;
	border-left: 0;
	border-right: 0;
}
.bar{
	height: 50px;
	background-color: #FFFFFF;
	position: absolute;
	bottom: 0px;
	width: 100%;
	border-top: 1px solid #F5F5F5;
}
.bar .select{
	width: 17px;
	height: 17px;
	border-radius: 50%;
	border: 1px solid #EEEEEE;
	margin-top: 16.5px;
	margin-left: 10px;
}
</style>
