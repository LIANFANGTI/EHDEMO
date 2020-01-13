<template>
	<view class="content">
		<view class="padding-xs bg-white">
			<tabs :items="items" theme="red"></tabs>
		</view>
		<view class="flex padding-xs  align-center bg-gradual-gray">
			<view class="flex-sub">公告:我是公告巴拉啦小魔仙全身变,可以把我关掉</view>
			<view class="cuIcon-close"></view>
		</view>
		<view class="padding-sm">
			  <view class="padding  flex    justify-between margin-top" style="background-image: url('../../static/image/bg-index-item.png');background-size: 100% 100%;" v-for="(item,index) in 3" :key="index">
				   <view class="text-custom-red padding-xs  solid-right  flex align-center justify-center">
					   <view>
						   <view class="text-price text-bold" style="font-size: 70rpx;">2-9</view>
						   <view>通用红包</view>
					   </view>
				   </view>
				   <view>
					    <view class="text-black text-lg">饿了么冬季补贴红包</view>
						<view class="flex margin-top">
							<view>平台:</view>
							<view class="text-blue margin-left-xs">饿了么</view>
						</view>
					   <view class="flex align-center margin-top-xs">
						   <view>有效期:</view>
						   <view class="text-red margin-left-xs">2020-01-09</view>
					   </view>

				   </view>
				   <view class="flex align-center justify-center ">
					   <button class="cu-btn bg-custom-gradual-orange round">免费领取</button>
				   </view>
			  </view>
		</view>

	</view>
</template>

<script>
	import Tabs from "../../component/tabs";
	export default {
		components: {Tabs},
		data() {
			return {
				title: 'Hello',
				items:["全部","饿了么红包","美团红包"]
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
		text-align: center;
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
</style>
