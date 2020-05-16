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
					 <view style="font-size: 30rpx;" class="text-bold">升级为店长</view>
					 <view class="text-sm">获得最高4%点餐返利权</view>
				 </view>
				 <view>
					 <button class="cu-btn round flex justify-between bg-custom-gradual-golden1 text-bold" @tap="showVipModel = true" >
						 <view class="text-sm" >点击开通</view>
						 <view class="round bg-black padding-2xs margin-left-xs">
							 <text class="cuIcon cuIcon-right "></text>
						 </view>
					 </button>
				 </view>
			 </view>
		 </view>
		 <view class="bg-white padding margin-top-sm">
			<view class="text-black text-lg text-bold">我的收益</view>


			<view class="flex justify-between  align-center">
				<view class="flex flex-sub  justify-center margin-right">
					<view class="bg-gray  bg-red  radius-xxxl padding-sm margin-top flex-sub">
						<view class="flex justify-between align-center text-sm">
							<text class="text-sm">累计收益</text>
							<text class="text-black" @tap="handleToIncome"> 查看 <text class="cuIcon-right"></text></text>
						</view>
						<view class="text-red text-bold margin-top-sm text-price margin-right-xl " style="font-size: 50rpx;">129.83</view>


					</view>
				</view>



				<view class="flex  flex-sub justify-center">
					<view class="bg-gray flex-sub radius-xxxl padding-sm margin-top flex-sub" >
						<view class="flex justify-between align-center text-sm">
							<text class="text-sm">可提现余额</text>
							<navigator url="./cashout" class="text-black flex align-center" @tap="handleToCashout"> 提现 <view class="cuIcon-right"></view></navigator>
						</view>
						<view class="text-red text-bold margin-top-sm text-price margin-right-xl " style="font-size: 50rpx;">29.873</view>


					</view>
				</view>
			</view>

		 </view>

		<view class="bg-white padding margin-top-sm">
			<view class="text-black text-lg  justify-between flex ">
				<view class="text-bold">我的团队</view>
				<view  class="text-sm  flex align-center text-gray" @tap="handleToFriend">
					<view class="text-black" >成员</view>
					<view class="cuIcon-right"></view>
				</view>
			</view>

			<view class="flex justify-between align-end">
				<view class="flex align-end margin-top text-bold">
					<view class="text-bold text-black" style="font-size: 50rpx;">123</view>
					<view>人</view>
				</view>
				<view class="flex">
					<view class="flex flex-direction align-center margin-right padding-right  solid-right ">
						<view class="text-bold text-xl">8</view>
						<view class="text-sm  text-gray">今日新增</view>
					</view>
					<view class="flex flex-direction align-center">
						<view class="text-bold text-xl">8</view>
						<view class="text-sm text-gray">昨日新增</view>
					</view>
				</view>
			</view>
		</view>

		<view class="bg-white padding margin-top-sm">
			<view class="text-black text-lg  justify-between flex ">
				<view class="text-bold">我的订单</view>
				<view  class="text-sm  flex align-center text-gray">
<!--					<view class="text-black" >详情</view>-->
					<navigator class="text-black"  url="./orders">详情</navigator>
					<view class="cuIcon-right"></view>
				</view>
			</view>

			<view class="flex justify-between align-end">
				<view class="flex align-end margin-top text-bold">
					<view class="text-bold text-black" style="font-size: 50rpx;">269</view>
					<view>单</view>
				</view>
				<view class="flex">
					<view class="flex flex-direction align-center margin-right padding-right  solid-right ">
						<view class="text-bold text-xl">8</view>
						<view class="text-sm  text-gray">今日新增</view>
					</view>
					<view class="flex flex-direction align-center">
						<view class="text-bold text-xl">8</view>
						<view class="text-sm text-gray">昨日新增</view>
					</view>
				</view>
			</view>
		</view>

		<view class="bg-white padding  flex justify-between align-center margin-top">
			<view>我的邀请人</view>
			<view class="cuIcon-right"></view>
		</view>


		<view class="bg-white padding  flex justify-between align-center margin-top">
			<view>联系客服</view>
			<view class="cuIcon-right"></view>
		</view>
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

<!--		<view class="bg-white padding margin-top-sm">-->
<!--			<view class="text-black text-lg text-bold"> 我的服务</view>-->
<!--			<view class="grid margin-top col-4 " >-->
<!--				 <view class="text-center    margin-top" v-for="(item,index) in services" :key="index">-->
<!--					  <view class="cuIcon cuIcon-moneybag text-custom-red" style="font-size: 60rpx;"></view>-->
<!--					 <view>{{item.title}}</view>-->
<!--				 </view>-->
<!--			</view>-->

<!--		</view>-->

	</view>
</template>

<script>
	import Avatar from "../../component/avatar";
	import Modal from "../../component/modal";
	export default {
		components: {Modal, Avatar},
		data() {
			return {
				title: 'Hello',
				showVipModel:false,
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
			handleToIncome(){
				uni.navigateTo({
					url:'../income/index'
				})
			},
			handleToCashout(){


			},
			handleToFriend(){
				uni.navigateTo({
					url:'../friend/index'
				})
			}



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
