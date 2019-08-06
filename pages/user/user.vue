<template>
	<view>
		<login v-if="islogin"></login>
		<view class="user">
			<view class="profile-home">
				<view class="mess">消息</view>
				<view class="set">设置</view>
				<view class="profile-head">
					<image src="../../static/images/cz.png" mode=""></image>
				</view>
				<view class="profile-name">大柚子</view>
				<view class="profile-signame">ID：475976</view>
			</view>
			<view class="profile-container">
				<view class="nav-item">
					<navigator url="recharge_record/recharge_record">
					<view class="item-title">0.00</view>
					<view class="item-desc">
						<text></text>
						金币
					</view>
					</navigator>
				</view>
				<view class="nav-item">
					<navigator url="integral_record/integral_record">
						<view class="item-title">0.00</view>
						<view class="item-desc">
							<text></text>
							积分
						</view>
					</navigator>
					
				</view>
				<view class="nav-item">
					<view class="item-title">0.00</view>
					<view class="item-desc">
						<text></text>
						红包
					</view>
				</view>
			</view>
			<view class="line"></view>
			<view class="slide-list">
				<view class="slide-item">
					<navigator url="recharge_money/recharge_money">
						<text></text>我要充值
					</navigator>
				</view>
			</view>
			<view class="line"></view>
			<view class="slide-list">
				<view class="slide-item">
					<navigator url="">
						<text></text>购买记录
					</navigator>
				</view>
				<view class="slide-item">
					<navigator url="recharge_record/recharge_record">
						<text></text>充值记录
					</navigator>
				</view>
				<view class="slide-item">
					<navigator url="win/win">
						<text></text>中奖商品
					</navigator>
				</view>
			<!-- 	<view class="slide-item">
					<navigator url="">
						<text></text>我的晒单
					</navigator>
				</view> -->
				<view class="slide-item">
					<navigator url="address/address">
						<text></text>收货地址
					</navigator>
				</view>
				<view class="slide-item">
					<navigator url="spread/spread">
						<text></text>推广赚钱
					</navigator>
				</view>
				<view class="slide-item">
					<navigator url="">
						<text></text>佣金记录
					</navigator>
				</view>
			</view>
			<view class="line"></view>
			<view class="slide-list">
				<view class="slide-item">
					<text></text>退出登录
				</view>
			</view>
			<view class="line"></view>
		</view>
	</view>
</template>

<script>
	import login from "../login/login"
	export default {
		components: {
			login
		},
		data() {
			return {
				islogin:false,
			};
		},
		onLoad() {
			const value = uni.getStorageSync('id');
			if(!value){
				// uni.navigateTo({
				// 	url:"../login/login"
				// })
				this.islogin = false;
			}
		}
	}
</script>

<style lang="scss">
body{
	height:100%;
}
uni-page-body{
	height: 100%;
	&>uni-view{
		height: 100%;
	}
}
.user{
	overflow-y: scroll;
	height: 100%;
	.profile-home{
		padding: 60upx 0 40upx;
		text-align: center;
		background-image: url("../../static/images/user_bg.png");
		background-position:center center;
		background-repeat: no-repeat;
		background-size: cover;
		background-color: #ff4c42;
		position: relative;
		.mess{
			position: absolute;
			top: 20upx;
			left: 30upx;
			color: #fff;
			font-size: 30upx;
		}
		.set{
			position: absolute;
			top: 20upx;
			right: 30upx;
			color: #fff;
			font-size: 30upx;
		}
		.profile-head{
			height: 152upx;
			width: 152upx;
			border-radius: 50%;
			border: 4upx solid #fff;
			margin: 0 auto;
			overflow: hidden;
			image{width: 100%;height: 100%;}
		}
		.profile-name{
			color: #fff;
			font-size: 36upx;
			font-weight: 600;
			padding: 10upx 0;
		}
		.profile-signame{
			color: #fff;
			font-size: 32upx;
		}
	}
	.profile-container{
		padding: 20upx 0;
		display: flex;
		.nav-item{
			flex: 1;
			border-right: 1upx solid #eee;
			text-align: center;
			.item-title{
				color: #ff4c42;
				padding-bottom: 10upx;
				font-size: 28upx;
			}
			.item-desc{
				font-size: 32upx;
			}
		}
	}
	.slide-list{
		.slide-item{
			navigator{
				padding: 0 30upx;
			}
			height: 80upx;
			line-height: 80upx;
			border-bottom: 1upx solid #eee;
			font-size: 30upx;
			color: #333;
		}
	}
}
</style>
