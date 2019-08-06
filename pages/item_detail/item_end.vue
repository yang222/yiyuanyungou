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
			<text>已揭晓</text>苹果iPhone XR 64GB全网通6.1英寸双卡双待4G手机 （颜色随机）
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
				<text class="right">剩余<text class="color">0</text>人次</text>
			</view>
		</view>
		<view class="operate-buys">
			<view class="detail-lottery">
				<image src="../../static/images/zjz.png" mode="" class="lottery-arrow"></image>
				<view class="lottery-uifo">
					<view class="lottery-head">
						<image src="../../static/images/cz.png" mode=""></image>
					</view>
					<view class="lottery-info">
						<view class="item">获奖者：<text class="b_color">再次中中迈停</text>（广东省深圳市移动 ） </view>
						<view class="item">用户ID：59828（唯一不变码）</view>
						<view class="item">期号：1907310010</view>
						<view class="item">本期参与：<text class="color">77</text>人次</view>
						<view class="item">揭晓时间：2019-08-01 17:05:36.000</view>
					</view>
				</view>
				<view class="lottery-detail">
					<view class="detail-arrow"></view>
					<text class="detail-num-desc" id="btnWinnerCodes" data="10002656">幸运号码：10002656</text>
					<navigator url="../lucky/lucky" class="url">查看详情</navigator>
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
				<text class="icon"></text>
				<text>图文详情</text>
				<text class="r">建议在wifi下查看</text>
			</view>
			<view class="slide-item"  @tap="wq">
				<text class="icon"></text>
				<text>往期揭晓</text>
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
				新一期正在火热进行中...
			<navigator url="item_detail" class="to">立即前往</navigator>
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
		padding-top: 40upx;
		.lottery-arrow{
		    position: absolute;
			left: -4upx;
			top: -4upx;
			width: 116upx;
			height: 110upx;
			z-index: 1;
			pointer-events: none;
		}
		.detail-lottery{
			box-shadow: 0 0 10px 0 rgba(50,50,50,.3);
			padding: 20upx;
			position: relative;
			font-size: 28upx;
			color: #4e4e4c;
		}
		.lottery-uifo{
			background: #fbf3f0;
			padding: 20upx;
			position: relative;
			padding-left: 20upx;
			box-sizing: border-box;
			display: flex;
			.lottery-head{
				width:100upx; 
				padding-right: 20upx;
				text-align: center;
				image{
					width: 100upx;
					height: 100upx;
					border-radius: 50%;
				}
			}
			.lottery-info{
				flex: 1;
				font-size: 26upx;
				.item{
					margin-bottom: 10upx;
				}
			}
		}
		.lottery-detail{
			font-size: 32upx;
			color: #fff;
			padding: 15upx 40upx;
			background: #EF3A4B;
			position: relative;
			line-height: 45upx;
			.detail-arrow{
				position: absolute;
				background: url(../../static/images/sj.png) repeat-x top left;
				height: 12upx;
				width: 100%;
				left: 0;
				top: -12upx;
				background-size: 20upx auto;
			}
			.url{
				float: right;
				height: 45upx;
				line-height: 45upx;
				border: 1upx solid #fff;
				border-radius: 6upx;
				font-size: 24upx;
				padding: 0 30upx;
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
		height: 60upx;
		padding: 20upx;
		text-align: center;
		left: 0;
		text-align: left;
		line-height: 60upx;
		font-size: 32upx;
		bottom: 0;
		border-top: 1upx solid #eee;
		background: #fff;
		.to{
			float:  right;
			height: 60upx;
			line-height: 60upx;
			padding: 0 20upx;
			font-size: 28upx;
			background: #ff4c42;
			border-radius: 6upx;
			margin-right: 40upx;
			color: #fff;
		}
	}
}
</style>
