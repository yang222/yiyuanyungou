<template>
	<view class="spread">
		<login v-if="islogin"></login>
		<view class="tg-img">
			<image src="../../../static/images/inv-ad.png" mode=""></image>
		</view>
		<view class="id">推广UID <text>475976</text>  截图保存海报分享好友</view>
		<button type="primary" class="primary" @tap="hbshow= true">推广宣传海报</button>
		<view class="txt">长按复制以下链接发送给好友</view>
		<view class="area" disabled="true" id="copy">{{val}}</view>
		<view class="wwcz">
			<view class="wwcz_l">
				<view class="color">0人</view>
				<text>邀请奖励</text>
				<view class="color">10积分</view>
			</view>
			<view class="wwcz_r">
				<view class="color">0元</view>
				<text>佣金</text>
				<view class="color">￥10</view>
			</view>
		
		</view>
		<view class="woqulist">
			<view class="item"><navigator url="../invite/invite">邀请记录 <text class="r iconfont iconyou-"></text></navigator></view>
			<view class="item"><navigator url="../commission/commission">佣金明细 <text class="r iconfont iconyou-"></text></navigator></view>
			<view class="item"><navigator url="../invite_note/invite_note">邀请说明 <text class="r iconfont iconyou-"></text></navigator></view>
		</view>
		<view class="layout" v-show="hbshow">
			<view class="cont">
				<text class="close" @tap="hbshow =false"></text>
				<view class="ewm"></view>
				<image src="../../../static/images/beijing.jpg" mode=""></image>
			</view>
		</view>
	</view>
</template>

<script>
	import login from "../../login/login"
	export default {
		components: {
			login
		},
		data() {
			return {
				val:"恭喜您免费获得1元抢iphone手机资格，快来看看吧！http://www.grils.cn/tg.php?y=yinzhuan&tuid=475976",
				islogin:false,
				hbshow:false,
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
		},
		methods:{
			copy(){
				try{
					if(uni.setClipboardData()){
						uni.setClipboardData({
							data: this.val,
							success: function () {
								uni.showToast({
									title: '复制成功！',
									duration: 1500
								});
							}
						});
					}else{
						var ee = document.getElementById("copy");

						document.execCommand("Copy"); // 执行浏览器复制命令
						uni.showToast({
							title: '复制成功！',
							duration: 1500
						});
					}
					
				}catch(e){
					var ee = document.getElementById("copy");
					ee.select(); // 选择对象
					document.execCommand("Copy"); // 执行浏览器复制命令
					uni.showToast({
						title: '复制成功！',
						duration: 1500
					});
				}
				
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
.spread{
	background: #fff;
	.tg-img{
		image{
			width: 100%;
			height: 243.75upx;
		}
	}
	.id{
		text-align: center;
		padding: 20upx 0;
		font-size: 32upx;
		color: #ff4c42;
		text{
			font-weight: 600;
			margin:  0 10upx;
			color: #000;
		}
	}
	.primary{
		width: 50%;
		margin: 30upx auto;
		background: #ff4c42;
	}
	.txt{
		color: #999;
		text-align: center;
		font-size: 30upx;
		margin-bottom: 10upx;
	}
	.area{
		width: 90%;
		height: 120upx;
		line-height: 50upx;
		margin: 0 auto;
		box-sizing: border-box;
		border: 1upx solid #aaa;
		padding: 10upx 10upx;
		font-size: 24upx;
		color: #999;
	}
	.warn{
		width: 40%;
		height: 70upx;
		line-height: 70upx;
		font-size: 30upx;
		margin-top: 30upx;
		margin-bottom: 20upx;
		background: #ff4c42;
	}
	.wwcz{
		display: flex;
		text-align: center;
		font-size: 30upx;
		padding: 20upx 0;
		border-bottom: 1upx solid #ccc;
		.wwcz_l{
			flex: 1;
			border-right:1upx solid #ccc;
			text{
				margin: 10upx 0;
				display: block;
				font-size: 32upx;
			}
		}
		.wwcz_r{
			flex: 1;
			text{
				margin: 10upx 0;
				display: block;
				font-size: 32upx;
			}
		}
	}
	.woqulist{
		height: 80upx;
		line-height: 80upx;
		.item{
			font-size: 30upx;
			padding: 0 30upx;
			border-bottom: 1upx solid #ccc;
			.iconfont{
				font-size: 40upx;
			}
		}
	}
	.layout{
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		background: rgba(0,0,0,0.6);
		.cont{
			position: absolute;
			width: 604upx;
			height: 1000upx;
			top: 50%;
			left: 50%;
			transform: translate(-50%,-50%);
			image{
				width: 100%;
				height: 100%;
			}
			.close{
				position: absolute;
				top: -30upx;
				right: -30upx;
				z-index: 10;
				width: 60upx;
				height: 60upx;
				background: url('../../../static/images/icon.png') no-repeat;
				background-size:420upx 122upx;
				background-position: -298upx -62upx;
			}
			.ewm{
				position: absolute;
				z-index: 10;
				width: 200upx;
				left: 50%;
				transform: translateX(-50%);
				height: 200upx;
				top: 270upx;
				background: #fff;
			}
		}
		
		
	}
}
</style>
