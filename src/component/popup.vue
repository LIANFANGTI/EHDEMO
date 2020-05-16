<template>
    <view v-if="showPopup" class="uni-popup" @touchmove.stop.prevent = "doNothing">
        <view :class="[ani, animation ? 'ani' : '', !custom ? 'uni-custom' : '']" class="uni-popup__mask" @click="close(true)" />
        <view :class="[type, ani, animation ? 'ani' : '', !custom ? 'uni-custom' : '']" class="uni-popup__wrapper flex align-center justify-center" @click="close(true)">
           <view class="flex-sub margin">
               <view class="  flex justify-end">
                    <view class="cuIcon-roundclose text-white" style="font-size: 60rpx;"></view>
               </view>
               <view class="bg-white padding margin-top-sm radius-xxl">
                   <slot ></slot>
               </view>

               <view class="flex bg-white padding-sm margin-top radius-xxl">
                   <view class="flex align-center">
<!--                       <avatar  size="xs" alpha></avatar>-->
                       <img src="../static/image/icon-share.png"></img>
                   </view>
                   <view class="margin-left text-left">
                       <view class="text-bold text-black">长按图片保存分享海报给好友</view>
                       <view class="text-gray">好友领红包点餐，赚最高 <text class="text-red">6%佣金</text></view>
                   </view>

               </view>

           </view>
        </view>
    </view>
</template>

<script>
    import Avatar from "./avatar";
    export default {
        name: 'UniPopup',
        components: {Avatar},
        props: {
            // 开启动画
            animation: {
                type: Boolean,
                default: true
            },
            // 弹出层类型，可选值，top: 顶部弹出层；bottom：底部弹出层；center：全屏弹出层
            type: {
                type: String,
                default: 'center'
            },
            title:String,
            // 是否开启自定义
            custom: {
                type: Boolean,
                default: false
            },
            customHeader:Boolean,
            // maskClick
            maskClick: {
                type: Boolean,
                default: true
            },
            value: {
                type: Boolean,
                default: false
            }
        },
        data() {
            return {
                ani: '',
                showPopup: false
            }
        },
        watch: {
            value(newValue) {
                if (newValue) {
                    this.open()
                } else {
                    this.close()
                }
            }
        },
        created() {
            if(this.value){
                this.open();
            }
        },
        methods: {
            doNothing(){},
            clear() {},
            open() {
                this.$emit('change', {
                    show: true
                });
                this.$emit("input",true);
                this.showPopup = true;
                this.$nextTick(() => {
                    setTimeout(() => {
                        this.ani = 'uni-' + this.type
                    }, 30)
                })
            },
            close(type) {
                if (!this.maskClick && type) return
                this.$emit('change', {
                    show: false
                });
                this.$emit("cancel",false);
                this.$emit("input",false);
                this.ani = '';
                this.$nextTick(() => {
                    setTimeout(() => {
                        this.showPopup = false
                    }, 300)
                })
            }
        }
    }
</script>
<style>

    .uni-popup {
        position: fixed;
        top: 0;
        top: 0;
        bottom: 0;
        left: 0;
        right: 0;
        z-index: 999;
        overflow: hidden
    }

    .uni-popup__mask {
        position: absolute;
        top: 0;
        bottom: 0;
        left: 0;
        right: 0;
        z-index: 998;
        background: rgba(0,0,0,0.75);
        opacity: 0
    }

    .uni-popup__mask.ani {
        transition: all .3s
    }

    .uni-popup__mask.uni-bottom,
    .uni-popup__mask.uni-center,
    .uni-popup__mask.uni-top {
        opacity: 1
    }

    .uni-popup__wrapper {
        position: absolute;
        z-index: 999;
        box-sizing: border-box
    }

    .uni-popup__wrapper.ani {
        transition: all .3s
    }

    .uni-popup__wrapper.top {
        top: 0;
        left: 0;
        width: 100%;
        transform: translateY(-100%)
    }

    .uni-popup__wrapper.bottom {
        bottom: 0;
        left: 0;
        width: 100%;
        transform: translateY(100%);
    }

    .uni-popup__wrapper.center {
        width: 100%;
        height: 100%;
        /*display: flex;*/
        justify-content: center;
        align-items: center;
        transform: scale(1.2);

        opacity: 0;
    }


    .uni-popup__wrapper-box {
        position: relative;
        box-sizing: border-box;
    }

    .uni-popup__wrapper.uni-custom .uni-popup__wrapper-box {
        /* padding: 30upx; */
        background: #fff;
        border-radius: 12px 12px 0px 0px;
    }

    .uni-popup__wrapper.uni-custom.center .uni-popup__wrapper-box {
        position: relative;
         max-width: 80%;
         width: 80%;
         max-height: 80%;
        overflow-y: scroll;
        border-radius: 12px 12px 12px 12px;

    }

    .uni-popup__wrapper.uni-custom.bottom .uni-popup__wrapper-box,
    .uni-popup__wrapper.uni-custom.top .uni-popup__wrapper-box {
        width: 100%;
        /* max-height: 500px; */
        overflow-y: scroll
    }

    .uni-popup__wrapper.uni-bottom,
    .uni-popup__wrapper.uni-top {
        transform: translateY(0)
    }

    .uni-popup__wrapper.uni-center {

        transform: scale(1);
        opacity: 1
    }


    </style>
