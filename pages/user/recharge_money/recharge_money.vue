<template>
	<view class="recharge_money">
		<view class="recharge-title">请选择充值金额</view>
		<view class="rec_input"><input type="text" placeholder="请输入充值金额" v-model="money"></view>
		<view class="money-list">
			<view class="money-item" v-for="(item,index) in money_list" :class="{'active':item == money}" :key="index" @tap="check(item)">{{item}}</view>
		</view>
		<view class="type-list">
			<view class="type-item" @tap="check_type(1)">
				<view class="type-title">
					<image src="../../../static/images/xwx.png" mode=""></image>
					微信APP内-识别扫码（推荐）
				</view>
				<view class="tx">
					请按照提示金额扫码付款,精确小数点后2位
				</view>
				<text class="chec"  :class="{'active':type == 1}"></text>
			</view>
			<view class="type-item" @tap="check_type(2)">
				<view class="type-title">
					<image src="../../../static/images/xyl.png" mode=""></image>
					银行卡网银转账-3分钟内到账
				</view>
				<view class="tx" >
					单笔金额赠送2%,使用各大银行APP转账充值
				</view>
				<text class="chec" :class="{'active':type == 2}"></text>
			</view>
			<view class="type-item" @tap="check_type(3)">
				<view class="type-title">
					<image src="../../../static/images/xxx.png" mode=""></image>
					微信/支付宝/线下转账-人工充值
				</view>
				<view class="tx">
					充值时间早9:00点-晚23:00点,单笔金额赠送2%
				</view>
				<text class="chec" :class="{'active':type == 3}"></text>
			</view>
			<button type="warn" class="pay_btn">立即支付</button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				money:"",
				money_list:[20,50,100,200,500,1000,2000,5000],
				type:1,
				
			};
		},
		methods:{
			check(item){
				this.money = item;
			},
			check_type(type){
				this.type = type;
			}
		}
	}
</script>

<style lang="scss">
.recharge_money{
	.recharge-title{
		padding: 20upx 30upx;
		font-size: 32upx;
		color: #333;
	}
	.rec_input{
		padding: 10upx 30upx;
		input{
			height: 70upx ;
			line-height: 70upx;
			border: 1upx solid #aaa;
			font-size: 30upx;
			padding-left: 10upx;
		}
	}
	.money-list{
		padding: 10upx;
		font-size: 0;
		text-align: center;
		.money-item{
			display: inline-block;
			width: 20%;
			margin: 0 2%;
			height: 60upx;
			border: 1upx solid #aaa;
			margin-bottom: 20upx;
			border-radius: 6upx;
			font-size: 30upx;
			color: #333;
			line-height: 60upx;
			cursor: pointer;
			&.active{
				color: #ff4c42;
				border-color: #ff4c42;
			}
		}
	}
	.type-list{
		.type-item{
			padding: 30upx;
			border-bottom: 1upx solid #eee;
			position: relative;
			cursor: pointer;
			.type-title{
				image{width: 70upx;height: 70upx;margin-right: 20upx;vertical-align: top;}
				line-height: 70upx;
				font-size: 32upx;
			}
			.tx{
				padding-top: 10upx;
				font-size: 28upx;
				color: #ff4c42;
			}
			.chec{
				position: absolute;
				top: 50%;
				right: 30upx;
				transform: translateY(-50%);
				width: 40upx;
				height: 40upx;
				border-radius: 50%;
				border: 1upx solid #aaa;
				&.active{
					background: #ff4c42;
					border-color: #ff4c42;
				}
			}
		}
	}
	.pay_btn{
		margin-top: 50upx;
		width: 80%;
	}
}
</style>
