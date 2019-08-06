<template>
	<view class="add_address">
		<view class="address-item">
			<text class="lab">收货人</text>
			<input type="text">
		</view>
		<view class="address-item">
			<text class="lab">手机号码</text>
			<input type="text" placeholder="请输入手机号码" maxlength="11">
		</view>
		<view class="address-item">
			<text class="lab">省份</text>
			 <picker @change="sChange" :value="index" :range="s_arr">
				<view class="uni-input">{{s_arr[index]}}</view>
			</picker>
		</view>
		<view class="address-item">
			<text class="lab">城市</text>
			 <picker @change="sChange" :value="index" :range="s_arr">
				<view class="uni-input">{{s_arr[index]}}</view>
			</picker>
		</view>
		<view class="address-item">
			<text class="lab">地区</text>
			 <picker @change="sChange" :value="index" :range="s_arr">
				<view class="uni-input">{{s_arr[index]}}</view>
			</picker>
		</view>
		<view class="address-item area">
			<text class="lab">详细地址</text>
			<textarea value="" placeholder="不需要重复填写省/市/区" />
		</view>
		<view class="address-last">
			<text class="lab">是否设置为默认地址</text>
			<switch class="r"  @change="switch1Change" />
		</view>
		<view class="address-last">
			<text class="color">删除收货地址</text>
		</view>
		<button type="warn" class="btn">保存地址</button>
	</view>
</template>

<script>
export default{
	data(){
		return{
			s_arr:['北京市'],
			index:0,
			id:"",
		}
	},
	onLoad(e){
		this.id = e.id;
	},
	methods:{
		sChange(){
			
		}
	}
}
</script>
<style lang="scss">
.add_address{
	.address-item{
		display: flex;
		height: 80upx;
		line-height: 80upx;
		border-bottom: 1upx solid #eee;
		font-size: 28upx;
		padding: 0 30upx;
		.lab{
			width: 200upx;
			color: #999;
		}
		input{
			height: 80upx;
			line-height: 80upx;
			font-size: 28upx;
		}
	}
	.area{
		height: 160upx;
		textarea{
			line-height: 45upx;
			padding-top: 15upx;
			font-size: 28upx;
			height: 140upx;
		}
	}
	.address-last{
		height: 80upx;
		line-height: 80upx;
		border-bottom: 1upx solid #eee;
		font-size: 28upx;
		padding: 0 30upx;
		.lab{
			width: 300upx;
			color: #999;
		}
	}
	.btn{
		width: 80%;
		margin-top: 100upx;
	}
}
</style>
