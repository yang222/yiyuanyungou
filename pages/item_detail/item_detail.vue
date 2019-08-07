<template>
	<view class="item-detail">
		<view class="detail-section swiper">
			<view class="page-section-spacing">
				<swiper class="swiper" :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration" indicator-color="#ddd" indicator-active-color="#ea4c4d">
					<swiper-item>
						<view class="swiper-item">
							<image src="../../static/images/bzqf.png" mode=""></image>
						</view>
					</swiper-item>
					<swiper-item>
						<view class="swiper-item">
							<image src="../../static/images/iphoex.png" mode=""></image>
						</view>
					</swiper-item>
					<swiper-item>
						<view class="swiper-item">
							<image src="../../static/images/xyzp.png" mode=""></image>
						</view>
					</swiper-item>
				</swiper>
			</view>
		</view>
		<view class="item-name">
			<text>进行中</text>苹果iPhone XR 64GB全网通6.1英寸双卡双待4G手机 （颜色随机）
		</view>
		<view class="desc">
			  新版亮点屏幕、Face ID、AR技术、无线充电和机身材质突破。 
		</view>
		<view class="jd">
			<view class="bg">
				<view class="cover"></view>
			</view>
			<view class="pep">
				<text class="left">满5899人次开奖</text>
				<text class="right">剩余<text class="color">4555</text>人次</text>
			</view>
		</view>
		<view class="operate-buys">
			<view class="buys_cont">
				<text class="type">购买方式</text>
				<view class="buys_l">
					<view>购买商品总价<text class="color">5888</text>金币</view>
					<view>单次价格<text class="color">1.00</text>金币 </view>
				</view>
				<view class="buys_r">
					<view class="btn">立即参与</view>
				</view>
			</view>
		</view>
		<view class="myCodes">
			<view class="codes">
				<navigator url="../login/login">请登录</navigator>查看你的乐购号码
			</view>
		</view>
		<view class="line"></view>
		<view class="slide-list">
			<view class="slide-item">
				<text class="icon iconfont icontupian"></text>
				<text>图文详情</text>
				<text class="r">建议在wifi下查看</text>
			</view>
			<view class="slide-item" @tap="wq">
				<text class="icon iconfont icondingdan"></text>
				<text >往期揭晓</text>
			</view>
		</view>
		<view class="line"></view>
		<view class="join-container">
			<view class="join-title">参入记录</view>
			<view class="join-item">
				<view class="img">
					<image src="../../static/images/cz.png" mode=""></image>
				</view>
				<view class="item">
					<view class="name">招财老爷来保号  河北省唐山市广电网 211.146.82.219</view>
					<view class="join-num">参与<text class="color">116人次</text>2019-08-01 15:13:25</view>
				</view>
			</view>
		</view>
		<uni-load-more  :loadingType="loadingType" :contentText="contentText" ></uni-load-more>
		<view class="footer-join-btns">
			<view class="join">
				立即参与
			</view>
			<view class="join-cart">
				加入购物车
			</view>
			<view class="cart iconfont iconunie62d" @tap="tocart">
				<text class="num">1</text>
			</view>
		</view>
		
	</view>
</template>

<script>
import uniLoadMore from '../../component/uni-load-more.vue';
var _self,page = 1,timer = null;
export default {
	components: {//2注册组件
		uniLoadMore
	},
	data() {
		return {
			indicatorDots: true,
			autoplay: true,
			interval: 2000,
			duration: 500,
			newsList: [],
			loadingText: '加载中...',
			loadingType: 2,//定义加载方式 0---contentdown  1---contentrefresh 2---contentnomore
			contentText: {
				contentdown:'上拉显示更多',
				contentrefresh: '正在加载...',
				contentnomore: '没有更多数据了'
			}
		}
	},
	onLoad: function() {
	    _self = this;
				//页面一加载时请求一次数据
	    this.getmorenews();
	},
	onPullDownRefresh: function() {
				//下拉刷新的时候请求一次数据
		page = 1;
		this.newsList = [];
	    this.getmorenews();
	},
	onReachBottom: function() {
			//触底的时候请求数据，即为上拉加载更多
			//为了更加清楚的看到效果，添加了定时器
	    if (timer != null) {
	        clearTimeout(timer);
	    }
	    timer = setTimeout(()=>{
			page++;
	        this.getmorenews();
	    }, 1000);
				
				// 正常应为:
				// _self.getmorenews();
	},
	methods: {
		tocart(){
			uni.switchTab({
				url:"../cart/cart"
			})
		},
		wq(){
			uni.navigateTo({
				url: '../wq/wq',
			});
		},
		getmorenews: function() {
	        if (this.loadingType !== 0) {//loadingType!=0;直接返回
	            return false;
	        }
			//每触底一次 page +1
	        this.loadingType = 1;
	        uni.showNavigationBarLoading();//显示加载动画
	        uni.request({
	            url:'https://demo.hcoder.net/index.php?user=hcoder&pwd=hcoder&m=list1&page=' + page,
	            method: 'GET',
	            success: (res)=>{
	                if (res.data == null) {//没有数据
	                    _self.loadingType = 2;
	                    uni.hideNavigationBarLoading();//关闭加载动画
	                    return;
	                }
	                
	                _self.newsList = _self.newsList.concat(res.data.split('--hcSplitor--'));//将数据拼接在一起
	                _self.loadingType = 0;//将loadingType归0重置
	                uni.hideNavigationBarLoading();//关闭加载动画
	            },
				error:function(err){
					uni.hideNavigationBarLoading();
				}
	        });
	    },
	},
	mounted() {
		uni.hideNavigationBarLoading();
	}
}
</script>

<style lang="scss">
.item-detail{
	padding-top: 10upx;
	padding-bottom: 120upx;
	.swiper-item{
		height: 100%;
		background: #fff;
		text-align: center;
		image{height: 100%}
	}
	.detail-section{
		height: 450upx;
		.page-section-spacing{height: 100%;}
		
		uni-swiper{
			height: 100% !important;
		}
	}
	.item-name{
		padding:0 20upx;
		padding-top: 40upx;
		font-size: 36upx;
		line-height: 50upx;
		text{
			display: inline-block;
			vertical-align: top;
			margin-top: 5upx;
			font-size: 24upx;
			height: 40upx;
			color: #3BB720;
			border-radius: 10upx;
			line-height: 40upx;
			padding: 0 10upx;
			border: 1upx solid #3BB720;
			margin-right: 10upx;
		}
	}
	.desc{
		padding: 0 20upx;
		font-size: 28upx;
		color: #666;
	}
	.jd{
		padding: 0 20upx;
		padding-top: 40upx;
		.bg{
			height: 16upx;
			width: 100%;
			background: #ddd;
			border-radius: 6upx;
			overflow: hidden;
			position: relative;
			.cover{
				position: absolute;
				height: 16upx;
				top: 0;
				left: 0;
				background: linear-gradient(left,#fcca37,#fc8a37);
				transition: width 1s ease;
				width: 11.3%;
			}
		}
		.pep{
			height: 40upx;
			margin-top: 10upx;
			.left{
				float: left;
				color: #333;
				font-size: 28upx;
			}
			.right{
				float: right;
				color: #333;
				font-size: 28upx;
				.color{color: #ea4c4d;}
			}
		}
			
	}
	.operate-buys{
		padding: 20upx;
		.buys_cont{
			background: #eee;
			padding-top: 70upx;
			position: relative;
			font-size: 28upx;
			display: flex;
			.type{
				position: absolute;
				height: 50upx;
				line-height: 50upx;
				text-align: center;
				font-size: 24upx;
				padding: 0 30upx;
				left: 0;
				top: 0;
				background: #ff4c42;
				color: #fff;
				border-bottom-right-radius: 60upx;
			}
			.buys_l{
				flex: 1;
				text-align: left;
				padding:  0 20upx 20upx;
				view{
					padding-left: 50upx;
					color: #666;
					margin-bottom: 10upx;
				}
				
			}
			.buys_r{
				width: 200upx;
				text-align: right;
				padding-right: 20upx;
				.btn{
					height: 60upx;
					display: inline-block;
					background: #ff4c42;
					width: 150upx;
					color: #fff;
					line-height: 60upx;
					border-radius: 6upx;
					text-align: center;
					font-size: 24upx;
					cursor: pointer;
				}
			}
		}
	}
	.myCodes{
		padding: 20upx;
		padding-top: 0;
		.codes{
			padding: 20upx;
			background: #eee;
			font-size: 28upx;
			text-align: center;
			color: #666;
			navigator{
				display: inline-block;
				color: #ff4c42;
			}
		}
	}
	.slide-list{
		.slide-item{
			height: 60upx;
			line-height: 60upx;
			padding: 20upx;
			font-size: 32upx;
			border-bottom: 1upx solid #eee;
			.icon{
				font-size: 32upx;
				margin-right: 10upx;
				&.icontupian{
					color: #3BB720;
					margin-right: 16upx;
				}
				&.icondingdan{
					color: rgb(255,221,102);
					font-size: 42upx;
				}
			}
		}
	}
	.join-container{
		background: #fff;
		.join-title{
			height: 70upx;
			line-height: 70upx;
			font-size: 32upx;
			padding-left: 50upx;
			border-bottom: 1upx solid #eee;
			color: #ff4c42;
		}
		.join-item{
			display: flex;
			padding: 20upx 0;
			.img{
				width:150upx; 
				padding-right: 10upx;
				text-align: center;
				image{
					width: 100upx;
					height: 100upx;
					border-radius: 50%;
				}
			}
			.item{
				flex: 1;
				border-bottom: 1upx solid #eee;
				&:last-child{
					border: none;
				}
				.name{
					font-size: 28upx;
				}
				.join-num{font-size: 26upx;padding: 20upx 0;color: #666;
					.color{margin-right: 30upx;}
				}
			}
		}
	}
	.footer-join-btns{
		position: fixed;
		width: 100%;
		height: 120upx;
		padding: 20upx;
		box-sizing: border-box;
		text-align: center;
		left: 0;
		bottom: 0;
		border-top: 1upx solid #eee;
		background: #fff;
		view{
			display: inline-block;
			vertical-align: top;
			margin:  0 16upx;
			height: 80upx;
			line-height: 80upx;
			font-size: 30upx;
			cursor: pointer;
		}
		.join{
			width: 250upx;
			background: #ff4c42;
			color: #fff;
			border-radius: 6upx;
		}
		.join-cart{
			width: 280upx;
			border: 1upx solid #ff4c42;
			color: #ff4c42;
			border-radius: 6upx;
		}
		.cart{
			width: 70upx;
			font-size: 60upx;
			position: relative;
			.num{
				position: absolute;
				width: 40upx;
				height: 40upx;
				border-radius: 50%;
				background: #ff4c42;
				color: #fff;
				font-size: 28upx;
				line-height: 40upx;
				top: -10upx;
				right: -10upx;
			}
		}
	}
}
</style>
