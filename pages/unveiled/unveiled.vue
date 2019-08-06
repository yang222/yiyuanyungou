<template>
	<view class="unveile">
		<view class="items">
			<view class="item-cont">
				<view class="imgs"></view>
				<view class="name">
					<navigator url="../hello/hello" open-type="navigate">
					     苹果iPhone XR 64GB全网通6.1英寸双卡双待4G手机 （颜色随机）
					</navigator>
				</view>
				<view class="parameter">
					<text class="lab">期号：</text><text class="val">123123213</text>
				</view>
				<view class="parameter">
					<text class="lab">获奖者：</text><text class="val" style="color: #007AFF;">123123213</text>
				</view>
				<view class="parameter">
					<text class="lab">参与人数：</text><text class="val">204</text>
				</view>
				<view class="parameter">
					<text class="lab">幸运号码：</text><text class="val" style="color: #ea4c4d;">123123213</text>
				</view>
				<view class="parameter">
					<text class="lab">揭晓时间：</text><text class="val">2019-7-29 19:15:14</text>
				</view>
			</view>
			<view class="item-cont">
				<view class="imgs"></view>
				<view class="name">
					<navigator url="../hello/hello" open-type="navigate">
					     苹果iPhone XR 64GB全网通6.1英寸双卡双待4G手机 （颜色随机）
					</navigator>
				</view>
				<view class="parameter">
					<text class="lab">期号：</text><text class="val">123123213</text>
				</view>
				<view class="parameter">
					<text class="lab">获奖者：</text><text class="val" style="color: #007AFF;">123123213</text>
				</view>
				<view class="parameter">
					<text class="lab">参与人数：</text><text class="val">204</text>
				</view>
				<view class="parameter">
					<text class="lab">幸运号码：</text><text class="val" style="color: #ea4c4d;">123123213</text>
				</view>
				<view class="parameter">
					<text class="lab">揭晓时间：</text><text class="val">2019-7-29 19:15:14</text>
				</view>
			</view>
	
				<!--3使用组件 -->
			<uni-load-more  :loadingType="loadingType" :contentText="contentText" ></uni-load-more>
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
        this.getnewsList();
    },
    onPullDownRefresh: function() {
				//下拉刷新的时候请求一次数据
        this.getnewsList();
    },
    onReachBottom: function() {
			//触底的时候请求数据，即为上拉加载更多
			//为了更加清楚的看到效果，添加了定时器
        if (timer != null) {
            clearTimeout(timer);
        }
        timer = setTimeout(function() {
            _self.getmorenews();
        }, 1000);
				
				// 正常应为:
				// _self.getmorenews();
    },
	methods: {
		getmorenews: function() {
            if (_self.loadingType !== 0) {//loadingType!=0;直接返回
                return false;
            }
			page++;//每触底一次 page +1
            _self.loadingType = 1;
            uni.showNavigationBarLoading();//显示加载动画
            uni.request({
                url:'https://demo.hcoder.net/index.php?user=hcoder&pwd=hcoder&m=list1&page=' + page,
                method: 'GET',
                success: function(res) {
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
        getnewsList: function() {//第一次回去数据
            page = 1;
            // this.loadingType = 0;
            uni.showNavigationBarLoading();
            uni.request({
                url: 'https://demo.hcoder.net/index.php?user=hcoder&pwd=hcoder&m=list1&page=1',
                method: 'GET',
                success: function(res) {
                    _self.newsList = res.data.split('--hcSplitor--');
                    uni.hideNavigationBarLoading();
                    uni.stopPullDownRefresh();//得到数据后停止下拉刷新
                },
				error:function(err){
					uni.hideNavigationBarLoading();
				}
            });
        }

	},
	mounted() {
		uni.hideNavigationBarLoading();
	}
}
</script>

<style lang="scss">
.unveile{
	.items{
		font-size: 0;
		text-align: left;
		background: #fff;
		padding-top: 20upx;
		.item-cont{
			padding: 20upx;
			display: inline-block;
			width: 50%;
			box-sizing: border-box;
			border-right: 1upx solid #eee;
			border-bottom: 1upx solid #eee;
			&:nth-child(2){
				border-right: none;
			}
			.imgs{
				height: 250upx;
				text-align: center;
				image{height: 100%;}
			}
			.name{font-size: 28upx;color: #000;line-height: 40upx;height: 80upx;overflow: hidden;padding: 6upx 0;}
			.parameter{
				display: flex;
				padding: 4upx 0;
				.lab{
					width: auto;
					color: #666;
					font-size: 27upx;
				}
				.val{
					flex: 1;
					color: #000;
					font-size: 27upx;
					text-overflow: ellipsis;
					white-space: nowrap;
					overflow: hidden;
				}
			}
		}
	}
}
</style>
