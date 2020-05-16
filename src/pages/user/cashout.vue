<template>
    <view class="content">
            <view class="padding-xl bg-white">
                <view class="">输入提现金额</view>
                <view class="solid-bottom flex  padding-top  padding-right padding-bottom-sm align-end ">
                   <text class="text-black text-bold" style="font-size: 60rpx;">￥</text>
                    <input class="  flex align-end text-black margin-left text-bold" placeholder="输入提现金额" style="font-size: 60rpx;"  value="29.875"></input>
                </view>
                <view class="margin-top">
                    当前可提现余额29.87元, <text class="text-blue margin-left">全部提现</text>
                </view>
            </view>
            <view class="bg-white margin-top padding">
                <view class="text-bold">提现说明;</view>
                <view class="margin-top-sm">1.提现至少少于0.3元;</view>
                <view  class="margin-top-xs">2.提现免手续费;</view>
                <view  class="margin-top-xs">3.选择相应金额提现，将直接到账微信钱包;</view>
                <view  class="margin-top-xs">4.申请提现后2个工作日内到账。;</view>
            </view>

        <view class="footer flex padding bg-white justify-center align-end ">
            <button class="bg-green round cu-btn padding-xl" style="width: 640rpx;">立即提现</button>
        </view>

    </view>
</template>

<script>
    import Avatar from "../../component/avatar";
    import UniPopup from "../../component/popup";

    export default {
        components: {UniPopup, Avatar},

        data() {
            return {
                title: 'Hello',
            }
        },
        onLoad() {

        },
        methods: {}
    }
</script>

<style>
    .content {
        height: 400 upx;
    }

    .logo {
        height: 200 upx;
        width: 200 upx;
        margin-top: 200 upx;
    }

    .title {
        font-size: 36 upx;
        color: #8f8f94;
    }

    .padding-2xs {
        padding: 7 upx;
    }

    .bg-custom-gradual-golden1 {
        background-image: linear-gradient(-45deg, #F2D896, #EBD9BF);
        /*background-image: linear-gradient(45deg, #CDA773, #F8E1C0,#E1C399,#ECD8BB);*/
        color: #5F1B0A;

    }

    .bg-custom-gradual-golden1 {
        background-image: linear-gradient(-45deg, #F2D896, #EBD9BF);
        /*background-image: linear-gradient(45deg, #CDA773, #F8E1C0,#E1C399,#ECD8BB);*/
        color: black;

    }

    /*	升级背景*/
    .bg-update {
        border-radius: 30px;
        border-bottom-left-radius: 0px;
        border-bottom-right-radius: 0px;
    }
</style>
