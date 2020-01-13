<template>
    <view class="lft-tabs" :class="layout==='vertical'? 'VerticalBox flex ' :''">
        <!--  垂直布局-->
        <block v-if="layout === 'vertical'" >
            <view class="bg-gray">
                <scroll-view class="VerticalNav nav" scroll-y scroll-with-animation :scroll-top="VerticalNavTop" style="height:calc(100vh - 100rpx)">
                    <view class="cu-item " :class="index==cur?' text-'+theme+' bg-white cur-ver ':''" v-for="(item,index) in items" :key="index" @tap='handleSelectChange(index)' data-id="index">
                        {{ item.name ? item.name : item}}
                    </view>
                </scroll-view>
            </view>
            <scroll-view  class="VerticalMain  bg-white flex-sub" scroll-y scroll-with-animation style="height:calc(100vh - 100upx)"
                          :scroll-into-view="'main-'+ mainCur" @scroll="VerticalMain">
                <slot></slot>
            </scroll-view>
        </block>
        <!--  水平布局-->
        <block v-else>
            <scroll-view scroll-x class=" nav     text-df" :class="'bg1-'+theme" scroll-with-animation :scroll-left="scrollLeft">

                <view class="flex justify-between text-center bg-white" >
                    <!--                <view>长度:{{items.length}}{{items}}</view>-->
                    <view class="cu-item  flex-sub" :class="index==cur?'text-'+theme+' cur':''" v-for="(item,index) in items" :key="index" @tap="handleSelectChange(index)" :data-index="index">
                        {{ item.name ? item.name : item}}
                    </view>
                </view>
            </scroll-view>
        </block>


    </view>
</template>

<script>
    export default {
        name: "tabs",
        created(){
            console.log(`调试:组件Tab加载成功`)
        },
        data(){
            return{
                scrollLeft:0,
                cur:0,
                tabCur: 0,
                mainCur: 0,
                verticalNavTop: 0,
                load: true
            }
        },
        props:{
            items:{
                type:Array,  // 属性类型
                default(){
                    return []
                }   // 默认值
            },
            layout:{
                type:String,
                default:'horizontal'   // 传入 horizontal 水平 或 vertical 垂直
            },
            theme:{
                type:String,
                default:'gray'
            },
            value:{
                type:Number,
                default:0
            }

        },
        watch:{
            value:{
                handler(nv,ov){
                    console.log(`调试:value发生变化`,nv )
                     this.cur = nv;  //否则为数字 直接赋值 cur
                }
            }
        },
        methods: {
            handleSelectChange(index){
                // console.log("Tabbar被点击 当前点击第",index)//console.log 是调试输出用的
                console.log(`调试:`, index);
                let value = this.items[index]['value']|| (this.items[index]['value'] === '' ? '' : this.items[index]);
                let item = this.items[index];
                this.cur= index;
                this.$emit("change",{index,value,item});
                console.log(`调试:input`,this.items[index],this.items[index]['value']  );
                this.$emit("input", index)
            },
            VerticalMain(e) {
                let scrollTop = e.detail.scrollTop + 10;
                console.log(`调试:`, scrollTop)
                // // #ifdef MP-ALIPAY
                // return false  //支付宝小程序暂时不支持双向联动
                // // #endif
                // let that = this;
                // let tabHeight = 0;
                // console.log(`调试:开始滚了`)
                // if (this.load) {
                //     for (let i = 0; i < this.items.length; i++) {
                //         let view = uni.createSelectorQuery().select("#main-" + this.items[i].id).boundingClientRect(this);
                //         view.fields({
                //             size: true
                //         }, data => {
                //             this.items[i].top = tabHeight;
                //             tabHeight = tabHeight + data.height;
                //             this.items[i].bottom = tabHeight;
                //         }).exec();
                //     }
                //     this.load = false
                // }
                // let scrollTop = e.detail.scrollTop + 10;
                // for (let i = 0; i < this.items.length; i++) {
                //     if (scrollTop > this.items[i].top && scrollTop < this.items[i].bottom) {
                //         this.verticalNavTop = (this.list[i].id - 1) * 50
                //         this.tabCur = this.list[i].id;
                //         this.cur= this.list[i].id;
                //         console.log(scrollTop)
                //         return false
                //     }
                // }
            }
        },

    }
</script>

<style scoped>
    .fixed {
        position: fixed;
        z-index: 99;
    }

    .VerticalNav.nav {
        width: 200upx;
        white-space: initial;
        /*background: red;*/
    }

    .VerticalNav.nav .cu-item {
        width: 100%;
        text-align: center;
        /*background-color: #fff;*/
        margin: 0;
        border: none;
        height: 50px;
        position: relative;
    }

    .VerticalNav.nav .cu-item.cur {
        background-color: #f1f1f1;
    }

    .VerticalNav.nav .cu-item.cur::after {
        content: "";
        width: 8upx;
        height: 30upx;
        border-radius: 10upx 0 0 10upx;
        position: absolute;
        background-color: currentColor;
        top: 0;
        right: 0upx;
        bottom: 0;
        margin: auto;
    }

    .VerticalBox {
        display: flex;
    }
    .cur-ver::before{
        content: "";
        width: 8upx;
        position: absolute;
        top: 0;
        left: 0;
        bottom: 0;
        background-color: currentColor;
    }

    .VerticalMain {
        /*background-color: #f1f1f1;*/
        /*flex: 1;*/
    }
    scroll-view{
        width: inherit;
    }

</style>
