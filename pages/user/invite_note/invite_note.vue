<template>
	<view class="invite_note">
       <view class="note_txt">
		   1级好友：指我直接邀请的好友。<br>
		   2级好友：指我的1级好友邀请的好友。<br>
		   3级好友：指我的2级好友邀请的好友。<br>
		   比如，我邀请A，A邀请B，B邀请C，C邀请D。A是我的一级邀请好友，B是我的二级邀请好友，C是我的三级邀请好友。<br>
		   如果A消费100元，我将获得9%的佣金即9元。<br>
		   如果B消费100元，A将获得9%的佣金即9元，我将获得3%的佣金即3元。<br>
		   如果C消费100元，B将获得3%的佣金即3元，A将获得3%的佣金即3元，我将获得1%的佣金即1元。<br>
		   如果D消费100元，C将获得1%的佣金即1元，B将获得3%的佣金即3元，A将获得1%的佣金即1元，我不获得佣金。<br>
		   推广积分用于幸运转盘使用，10积分抽奖1次。<br>
		   充值佣金满100元可直接在线申请提现。
	   </view>
	   <view class="line"></view>
		<view class="list">
			<view class="item">
			   <view class="item_l"><text class="color">1</text>&nbsp; 级好友 充值赠送</view>
			   <view class="item_r">佣金 9%</view>
			</view>
			<view class="item">
			   <view class="item_l"><text class="b_color">2</text>&nbsp; 级好友 充值赠送</view>
			   <view class="item_r">佣金 3%</view>
			</view>
			<view class="item">
			   <view class="item_l"><text class="">3</text> &nbsp;级好友 充值赠送</view>
			   <view class="item_r">佣金 1%</view>
			</view>
		</view>
		<button type="warn" class="warn">立即赚钱</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
.invite_note{
	.note_txt{
		padding: 20upx;
		font-size: 28upx;
		text-align: left;
	}
	.item{
		height: 70upx;
		line-height: 70upx;
		display: flex;
		font-size: 28upx;
		padding: 0 30upx;
		border-bottom: 1upx solid #ddd;
		.item_l{
			flex: 1;
		}
		.item_r{
			width: 200upx;
			color: #ff4c42;
			text-align: right;
			font-weight: 600;
		}
	}
	.warn{
		margin-top: 50upx;
		height: 70upx;
		line-height: 70upx;
		font-size: 30upx;
		width: 80%;
	}
}
</style>
