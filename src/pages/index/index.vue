<template>
	<view class="content">
		<view class="padding " style="padding-bottom: 0px;">
			<view class="bg-red radius-xxxl padding" style="border-bottom-left-radius: 0px;border-bottom-right-radius: 0px; ">
				 <view class="flex justify-between align-center">
				   <view>我的累计收入:</view>
					<button class="cu-btn bg-custom-gradual-golden round" @tap="showVipModel = true">开通店长</button>
				 </view>
				<view class="flex justify-between align-center margin-top-xs">
					<view class="flex align-end ">
						<view class="text-bold margin-right-sm" style="font-size: 50rpx;">0</view>
						<view class="margin-bottom-xs">元</view>
					</view>
					<view class="text-sm">享受最高4%点餐返现</view>
				</view>

			</view>

		</view>
		<view class="padding-xs bg-white">
			<tabs :items="items" theme="red"></tabs>
		</view>
<!--		<view class="flex padding-xs  align-center bg-gradual-gray">-->
<!--			<view class="flex-sub">公告:我是公告巴拉啦小魔仙全身变,可以把我关掉</view>-->
<!--			<view class="cuIcon-close"></view>-->
<!--		</view>-->
		<view class="padding-sm">
			  <view class="padding  flex    justify-between margin-top" style="background-image: url('../../static/image/bg-index-item.png');background-size: 100% 100%;" v-for="(item,index) in 3" :key="index">
				   <view class="flex">
					   <view class="text-custom-red padding-xs  solid-right  flex align-center justify-center padding-right margin-right">
						   <view>
							   <view class="text-price text-bold" style="font-size: 60rpx;">2-9</view>
							   <view>通用红包</view>
						   </view>
					   </view>
					   <view class="text-sm text-left">
						   <view class="text-black text-bold">饿了么冬季补贴红包</view>
						   <view class="flex margin-top">
							   <view>平台:</view>
							   <view class="text-blue margin-left-xs">饿了么</view>
							   `</view>
						   <view class="flex align-center margin-top-xs">
							   <view>有效期:</view>
							   <view class="text-red margin-left-xs">2020-01-09</view>
						   </view>

					   </view>
				   </view>
				   <view class="flex align-center justify-center flex-direction  ">
					   <button class="cu-btn bg-custom-gradual-orange round text-sm" >免费领取</button>
					   <view class="flex margin-top align-center text-gray">
						   <view class="cuIcon cuIcon-share"></view>
						   分享
					   </view>
				   </view>
			  </view>
		</view>
		<view class="margin-top bg-white padding radius-xxl">
			<view class="flex   padding-sm justify-between">
				<view class="text-left">
					<view class="text-bold text-lg">邀请好友 <text class="text-dark-golden">得20%收益！</text></view>
					<view class="text-sm text-gray">好友点餐，我赚佣金（永久有效）</view>
				</view>
				<view class="flex align-center  justify-center">
					<button class="cu-btn  shadow-blur bg-custom-gradual-blue
						   round " @tap="showPosterPopup = true">立即邀请</button>
				</view>

			</view>

			<view class=" padding flex justify-between text-sm text-gray">
				<view class="flex flex-direction align-center">
					<avatar round src="../../static/image/icon-get-redpack.png"></avatar>
					<!--					<img src="../../static/image/icon-get-redpack.png"/>-->
					<!--					<svg v-else :class="svgClass" aria-hidden="true" v-on="$listeners">-->
					<!--						<use href="" />-->
					<!--					</svg>-->
					<text class="margin-top-sm">好友领红包</text>
				</view>
				<view class="flex flex-direction align-center">
					<avatar round src="../../static/image/icon-eleme.png"></avatar>
					<text class="margin-top-sm">好友下单点餐</text>
				</view>
				<view class="flex flex-direction align-center">
					<avatar round src="../../static/image/icon-back.png"></avatar>
					<text class="margin-top-sm">我拿6%佣金</text>
				</view>



			</view>
		</view>

		<view class="padding margin-top-sm bg-white padding margin radius-xxl">
			 <view class="text-bold text-black flex">注意事项</view>
			 <view class="text-left text-sm text-gray margin-top">
				 <view>1、普通会员可以每日来领券，无返利。成为店长后领券 下单可以获取返利，返利按照实际支付金额计算。</view>
				 <view>2、每天均可以领券，每次领券后，券的有效期为7天， 7天内使用领的券下任意单，每单均有返利。</view>
				 <view>3、饿了返利内测期间，返利次日24小时内结算。今天 下单，返利次日可以查看并提现。 </view>
				 <view>4、每次领券或者发券，请重新生成一张最新的二维码。</view>

			 </view>
			<view class="position-absolute  " style="left: 0px;width: 200rpx; z-index: 99;top: 120vh;" @tap="handleShare">
				<img  src="../../static/image/icon-money-pack.png"   class="position-relative" style="top: 25rpx;width: 100rpx;height: 100rpx;">

				<view class="bg-red padding-xs padding-top-sm padding-right-sm  padding-left-sm round flex align-end " style="border-bottom-left-radius: 0px;border-top-left-radius: 0px;">分享给好友</view>
			</view>

		</view>
		<uni-popup v-model="showPosterPopup" >
			<view class="flex align-center justify-center" style="height: 840rpx;">海报</view>
		</uni-popup>

		<modal v-model="showVipModel" title="开通店长" >
			<view >
				<view class="text-sm text-bold padding-bottom" style="border-bottom: 2px dashed #979797;">
					<view class="text-bold text-sm flex padding-xs ">1.每天可领取最高10元大额外卖红包</view>
					<view class="flex bg-light-pink   padding-xs radius  align-center margin-top-sm">
						<text class="cuIcon text-orange cuIcon-choicenessfill"></text>
						<text class="margin-left-xs ">2.可使用红包点餐，享返利</text>
					</view>
					<view class="flex bg-light-pink  padding-xs radius  align-center margin-top-sm">
						<text class="cuIcon text-orange cuIcon-choicenessfill"></text>
						<text class="margin-left-xs ">3.团队成员点餐，持续赚返利</text>
					</view>
				</view>
				<view class="padding  bg-light-pink solid   margin-top ">
					<view class="cu-tag bg-blue badge-left radius ">限时福利</view>
					<view class="flex justify-center">
						<view class="flex align-end">
							<view class="text-price text-red text-bold" style="font-size: 60rpx;">9.9</view>
							<view class="text-throu margin-bottom-xs text-gray margin-left-sm">50元</view>
						</view>
					</view>
					<view>3个月</view>
				</view>
			</view>
			<view slot="footer">
				<view class="padding bg-custom-gradual-orange">
					立即支付
				</view>
			</view>
		</modal>
		<view class="padding-xl"></view>
	</view>
</template>

<script>
	import Tabs from "../../component/tabs";
	import Svg from "vue-svgicon"
	import Avatar from "../../component/avatar";
	import UniPopup from "../../component/popup";
	import Modal from "../../component/modal";
	export default {
		components: {Modal, UniPopup, Avatar, Tabs,Svg},
		data() {
			return {
				title: 'Hello',
				items:["全部(3)","饿了么红包(2)","美团红包(1)"],
				showPosterPopup:false,
				showVipModel:false,
			}
		},
		onLoad() {

		},
		methods: {
			handleShare(){
				console.log(`调试:点击了分享` )
				this.showPosterPopup = true
			}
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
