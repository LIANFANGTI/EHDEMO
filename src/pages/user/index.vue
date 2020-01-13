<template>
	<view class="content">
		 <view class="bg-white  padding">
			 <view class="flex  align-center">
				 <view class="flex">
					 <avatar round src="http://img5.imgtn.bdimg.com/it/u=1646340667,588080170&fm=26&gp=0.jpg"></avatar>
				 </view>
				 <view class="margin-left">
					 <view  class="align-center  flex "> <text class="text-bold text-lg">蔡英文 </text> <text class="cu-tag radius bg-custom-gradual-golden1 margin-left-sm">普通会员</text> </view>
					 <view class="margin-top-sm">UID:3838438</view>
				 </view>
			 </view>
			 <view class="bg-black bg-update  padding margin-top flex justify-between align-center">
				 <view>
					 <view style="font-size: 42rpx;" class="text-bold">升级钻石会员</view>
					 <view>享受更多权益,佣金升级</view>
				 </view>
				 <view>
					 <button class="cu-btn round flex justify-between bg-custom-gradual-golden1 text-bold" >
						 立即升级
						 <view class="round bg-black padding-2xs margin-left-xs">
							 <text class="cuIcon cuIcon-right "></text>
						 </view>
					 </button>
				 </view>
			 </view>
		 </view>
		 <view class="bg-white padding margin-top-sm">
			<view class="text-black text-lg text-bold"> 我的钱包</view>
			 <view class="flex">
				 <view class="bg-gray radius-xxxl padding-sm margin-top flex-sub" style="background-image: url(../../static/image/bg-item.png);background-size: 100% 100%;">
					 <view class="flex justify-between">
						 <text>可提现余额</text>
						 <text class="text-black"> 提现 <text class="cuIcon-right"></text></text>
					 </view>
					 <view class="text-red text-bold margin-top-sm text-price margin-right-xl " style="font-size: 60rpx;">29.873</view>


				 </view>
				 <view class="flex-sub"></view>
			 </view>

		 </view>
		<view class="bg-white padding margin-top-sm">
			<view class="text-black text-lg text-bold"> 我的服务</view>
			<view class="grid margin-top col-4 " >
				 <view class="text-center    margin-top" v-for="(item,index) in services" :key="index">
					  <view class="cuIcon cuIcon-moneybag text-custom-red" style="font-size: 60rpx;"></view>
					 <view>{{item.title}}</view>
				 </view>
			</view>

		</view>

	</view>
</template>

<script>
	import Avatar from "../../component/avatar";
	export default {
		components: {Avatar},
		data() {
			return {
				title: 'Hello',
				services:[
					{title:'收益明细', icon:''},
					{title:'新手必看', icon:''},
					{title:'常见问题', icon:''},
					{title:'联系客服', icon:''},
					{title:'意见反馈', icon:''},
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
	.content {
		height: 400upx;
	}

	.logo {
		height: 200upx;
		width: 200upx;
		margin-top: 200upx;
	}

	.title {
		font-size: 36upx;
		color: #8f8f94;
	}
	.padding-2xs {
		padding: 7upx;
	}

	.bg-custom-gradual-golden1{
		background-image: linear-gradient(-45deg, #F2D896, #EBD9BF);
		/*background-image: linear-gradient(45deg, #CDA773, #F8E1C0,#E1C399,#ECD8BB);*/
		color: #5F1B0A;

	}
	.bg-custom-gradual-golden1{
		background-image: linear-gradient(-45deg, #F2D896, #EBD9BF);
		/*background-image: linear-gradient(45deg, #CDA773, #F8E1C0,#E1C399,#ECD8BB);*/
		color: black;

	}
/*	升级背景*/
	.bg-update{
		border-radius: 30px;
		border-bottom-left-radius: 0px;
		border-bottom-right-radius: 0px;
	}
</style>
