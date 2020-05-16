<template>
   <view>
       <view class="padding bg-white">
            <tabs :items="['昨天','前天','本月','上月']" theme="red"></tabs>
       </view>
       <view class="  ">

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
    import Tabs from "../../component/tabs";
    export default {
        name: "orders",
        components: {Tabs},
        data() {
            return {}
        },
        method: {}
    }
</script>

<style scoped>

</style>
