<template>
	<view>
		<login v-if="islogin"></login>
		<view class="cart" v-else>
			<view class="nodata" v-if="datalist.length ==0">
				
				购物车空空如也
				<button type="warn" class="btn" @tap="toshop">继续乐购</button>
			</view>
			<view class="cart_cont" v-else>
				<view class="cart-item">
					<view class="item-l">
						<image src="../../static/images/qrcode.png" mode=""></image>
					</view>
					<view class="item-r">
						<view class="name">苹果iPhone XR 64GB全网通6.1英寸双卡双待4G手机 （颜色随机）</view>
						<view class="num">总需：5899 人次，剩余 <text class="b_color">3232</text>人次</view>
						<view class="operate-bars">
							参与人次
							<view class="choose">
								<text class="cancel">-</text>
								<input type="number" value="" class="number" />
								<text class="add">+</text>
							</view>
							<view class="del">删除</view>
						</view>
						<view class="djiandd">
							单价<text class="color">1.00</text>金币
						</view>
						<view class="baowei">
							<text>3</text>
							<text>10</text>
							<text>20</text>
							<text>50</text>
							<text>包尾</text>
						</view>
					</view>
				</view>
				<view class="cart-item">
					<view class="item-l">
						<image src="../../static/images/qrcode.png" mode=""></image>
					</view>
					<view class="item-r">
						<view class="name">苹果iPhone XR 64GB全网通6.1英寸双卡双待4G手机 （颜色随机）</view>
						<view class="num">总需：5899 人次，剩余 <text class="b_color">3232</text>人次</view>
						<view class="operate-bars">
							参与人次
							<view class="choose">
								<text class="cancel">-</text>
								<input type="number" value="" class="number" />
								<text class="add">+</text>
							</view>
							<view class="del">删除</view>
						</view>
						<view class="djiandd">
							单价<text class="color">1.00</text>金币
						</view>
						<view class="baowei">
							<text>3</text>
							<text>10</text>
							<text>20</text>
							<text>50</text>
							<text>包尾</text>
						</view>
					</view>
				</view>
				<view class="cart-item">
					<view class="item-l">
						<image src="../../static/images/qrcode.png" mode=""></image>
					</view>
					<view class="item-r">
						<view class="name">苹果iPhone XR 64GB全网通6.1英寸双卡双待4G手机 （颜色随机）</view>
						<view class="num">总需：5899 人次，剩余 <text class="b_color">3232</text>人次</view>
						<view class="operate-bars">
							参与人次
							<view class="choose">
								<text class="cancel">-</text>
								<input type="number" value="" class="number" />
								<text class="add">+</text>
							</view>
							<view class="del">删除</view>
						</view>
						<view class="djiandd">
							单价<text class="color">1.00</text>金币
						</view>
						<view class="baowei">
							<text>3</text>
							<text>10</text>
							<text>20</text>
							<text>50</text>
							<text>包尾</text>
						</view>
					</view>
				</view>
				<view class="cart-item">
					<view class="item-l">
						<image src="../../static/images/qrcode.png" mode=""></image>
					</view>
					<view class="item-r">
						<view class="name">苹果iPhone XR 64GB全网通6.1英寸双卡双待4G手机 （颜色随机）</view>
						<view class="num">总需：5899 人次，剩余 <text class="b_color">3232</text>人次</view>
						<view class="operate-bars">
							参与人次
							<view class="choose">
								<text class="cancel">-</text>
								<input type="number" value="" class="number" />
								<text class="add">+</text>
							</view>
							<view class="del">删除</view>
						</view>
						<view class="djiandd">
							单价<text class="color">1.00</text>金币
						</view>
						<view class="baowei">
							<text>3</text>
							<text>10</text>
							<text>20</text>
							<text>50</text>
							<text>包尾</text>
						</view>
					</view>
				</view>
			</view>
			<view class="footer">
				共0件商品，<text class="color">0</text>个金币
				<button type="warn" class="warn">结算</button>
			</view>
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
				datalist:["1"],
			}
		},
		onLoad() {
			const value = uni.getStorageSync('id');
			if(!value){
				this.islogin = false;
			}
		},
		methods: {
			toshop(){
				uni.switchTab({
					url:"../classify/classify"
				})
			}
		}
	}
</script>

<style lang="scss">
body{
	min-height:100%;
}
uni-page-body{
	min-height: 100%;
	&>uni-view{
		min-height: 100%;
		background: #f7f7f7;
	}
}
.cart{
	padding-bottom: 120upx;
	.nodata{
		padding-top: 100upx;
		text-align: center;
		font-size: 30upx;
		color: #999;
		.btn{
			width: 30%;
			height: 70upx;
			line-height: 70upx;
			font-size: 30upx;
			margin-top: 50upx;
		}
	}
	.cart_cont{
		
		.cart-item{
			display: flex;
			padding: 30upx 20upx;
			background: #fff;
			border-bottom: 1upx solid #eee;
			.item-l{
				width: 128upx;
				height: 128upx;
				image{
					width: 100%;
					height: 100%;
				}
			}
			.item-r{
				flex: 1;
				padding-left: 20upx;
				.name{
					font-size: 30upx;
				}
				.num{
					font-size: 28upx;
					color: #999;
					padding: 10upx 0 15upx;
				}
				.operate-bars{
					font-size: 28upx;
					line-height: 70upx;
					color: #999;
					.choose{
						display: inline-block;
						vertical-align: top;
						margin: 0 20upx;
						border: 1upx solid #ddd;
						border-radius: 10upx;
						font-size: 0;
						font-size: 40upx;
						text-align: center;
						.cancel,.add{
							display:inline-block;
							width: 50upx;
							vertical-align: top;
							height: 70upx;
							cursor: pointer;
						}
						.number{
							display: inline-block;
							width: 100upx;
							height: 70upx;
							vertical-align: top;
							font-size: 30upx;
							border-left: 1upx solid #ddd;
							border-right: 1upx solid #ddd;
						}
					}
					.del{
						display: inline-block;
						width: 60upx;
						height: 60upx;
						line-height: 60upx;
						border: 1upx solid #ff4c42;
						color: #ff4c42;
						font-size: 24upx;
						border-radius: 50%;
						text-align: center;
					}
				}
				.djiandd{font-size: 24upx;padding-top: 10upx;color: #666;padding-bottom: 10upx;}
				.baowei{
					text{
						display: inline-block;
						vertical-align: top;
						height: 60upx;
						line-height: 60upx;
						padding: 0 20upx;
						background: #ff4c42;
						color: #fff;
						margin-right: 20upx;
						font-size: 24upx;
						cursor: pointer;
						border-radius: 6upx;
					}
				}
			}
		}
	}
	.footer{
		position: fixed;
		bottom: 100upx;
		left: 0;
		width: 100%;
		height: 100upx;
		line-height: 100upx;
		background: #fff;
		font-size: 30upx;
		padding: 0 30upx;
		box-sizing: border-box;
		.warn{
			float: right;
			height: 60upx;
			line-height: 60upx;
			width: 120upx;
			font-size: 30upx;
			margin-top: 20upx;
		}
	}
}
</style>
