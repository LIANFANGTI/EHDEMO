<template>
	<view class="content">
		 <view class="padding bg-black header " >
			 <view class="margin-top">好友团人数</view>
			 <view class="flex">
				 <view class="flex align-end">
					 <view class="text-bold" style="font-size: 60rpx;">123</view>
					 <view>人</view>
				 </view>
				 <view class="flex align-start margin-left">
					 <view class="bg-red padding-xs  custom-tag text-sm  ">新增12人</view>
				 </view>
			 </view>

			 <view class="bg-custom-gradual-golden text-center radius-xxxl flex padding position-relative justify-between" style="bottom:-34rpx; z-index: 10;">
				  <view class="flex-sub">
					  <view>获得利益</view>
					  <view class="text-price" style="font-size: 48rpx;">29.836</view>
				  </view>
				 <view class="" style="width: 1px;background: #36343A;"></view>
				  <view class="flex-sub">
					  <view>有效订单</view>
					  <view class="text-price"  style="font-size: 48rpx;">36</view>

				  </view>
			 </view>
		 </view>
		<view class=" bg-white " style="padding-top: 100rpx;">
			<view class="flex   padding justify-between">
				<view class="flex align-center">
					<view class="bg-red"  style="height: 64rpx;width: 70rpx;background: url(../../static/image/icon-addfriend.png);background-size: 100% 100%;"></view>
				</view>

				<view class="">
					<view class="text-bold text-lg">邀请好友 <text class="text-dark-golden">得20%收益！</text></view>
					<view class="">好友点餐，我赚佣金（永久有效）</view>
				</view>
				<view class="flex align-center  justify-center">
					<button class="cu-btn  shadow-blur bg-custom-gradual-orange round ">立即邀请</button>
				</view>

			</view>

		</view>
		<view class="bg-white padding margin-top-sm">
			 <view class="flex justify-between margin-top-sm solid-bottom padding-sm" v-for="(item,index) in 6" :key="index">
				 <view class="flex">
					 <view>
						 <avatar round src="https://dss1.baidu.com/6ONXsjip0QIZ8tyhnq/it/u=1413379684,507496555&fm=58"></avatar>
					 </view>
					 <view class="margin-left  ">

						 <view class="text-df text-black ">特朗普</view>
						 <view class="text-gray">注册时间: 2020/01/09 23:45:43</view>
					 </view>
				 </view>


				 <view class="flex align-center align-center " >
					 佣金 <text class="margin-left-sm text-black  text-price text-bold">2.1</text>
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
				title: 'Hello'
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
