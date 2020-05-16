<template>
	<view class="content">
		 <view class="padding bg-black header " >
			 <view class="margin-top">累计预估收益</view>
			 <view class="flex">
				 <view class="flex align-end">
					 <view class="text-bold  flex align-end margin-right-xs" style="font-size: 60rpx;padding-bottom: -100rpx;">123.4</view>
					 <view class=" padding-bottom-xs">元</view>
				 </view>
<!--				 <view class="flex align-start margin-left">-->
<!--					 <view class="bg-red padding-xs  custom-tag text-xs  ">新增12人</view>-->
<!--				 </view>-->
			 </view>

			 <view class="bg-custom-gradual-golden text-center radius-xxxl flex padding position-relative justify-between" style="bottom:-34rpx; z-index: 10;">
				  <view class="flex-sub text-sm">
					  <navigator  url="../user/orders">
						  <text>昨日预估</text>
						  <text class="cuIcon-right"></text>
					  </navigator>
					  <view class="text-price text-bold" style="font-size: 38rpx;">29.836</view>
				  </view>
				 <view class="" style="width: 1px;background: #36343A;"></view>
				  <view class="flex-sub text-sm">
					  <navigator  url="../user/orders">
						  <text>本月预估</text>
						  <text class="cuIcon-right"></text>
					  </navigator>
					  <view class="text-price text-bold"  style="font-size: 38rpx;">136.32</view>

				  </view>
			 </view>
		 </view>

		<view class=" bg-white " style="padding-top: 50rpx;">
			<view class="flex   padding justify-between">
				<view class="flex">
					<view class="flex align-center " >
						<view class="bg-red"  style="height: 64rpx;width: 68rpx;background: url(../../static/image/icon-addfriend.png);background-size: 100% 100%;"></view>
					</view>

					<view class="margin-left">
						<view class="text-bold text-lg">邀请好友 <text class="text-dark-golden">得20%收益！</text></view>
						<view class="text-sm">好友点餐，我赚佣金（永久有效）</view>
					</view>
				</view>
				<view class="flex align-center  justify-center">
					<button class="cu-btn  shadow-blur bg-custom-gradual-orange round ">立即邀请</button>
				</view>

			</view>

		</view>

		<view class=" margin-top-sm bg-white">

			<view class="table text-sm ">
				<view class="th ">
					 <view class="td">日期</view>
					 <view class="td">订单号</view>
					 <view class="td">订单金额</view>
					 <view class="td">返现</view>
					 <view class="td">下单者</view>
				</view>
				<view class="tr " v-for="(item,index) in 4" :key="index">
					 <view class="td text-black text-bold">2020/1/2</view>
					 <view class="td">20202...563</view>
					 <view class="td">
						 <text class="text-price">16.7</text>
					 </view>
					<view class="td">
						<text class="text-price text-bold text-black">1.9</text>
					</view>
					<view class="">
						<view class="flex align-center">
							<view>Whale</view>
							<view class="bg-red radius text-xs margin-left-xs">直推</view>
						</view>


					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	import Avatar from "../../component/avatar";
	import Tabs from "../../component/tabs";
	export default {
		components: {Tabs, Avatar},
		data() {
			return {
				title: 'Hello',
				items:["汇总(123)","店长","经理","普通会员"]
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
	.header{
		height: 280rpx;
		background-image: url("../../static/image/bg-firend-head.png");
		background-size: 100% 100%;
	}
		.custom-tag{
			border-radius: 30px;
			border-bottom-left-radius: 0px;
		}
	.logo {
		height: 200upx;
		width: 200upx;
	}

	.title {
		font-size: 36upx;
		color: #8f8f94;
	}


</style>
