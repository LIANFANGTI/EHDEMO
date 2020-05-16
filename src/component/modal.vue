<template>
    <view class="cu-modal" :class="show?'show':''"  @tap="handleModalClose" >
        <view class="cu-dialog" :style="{maxWidth: maxWidth }">
            <view class="cu-bar bg-white justify-end" v-if="!hideHeader">
                <view class='content text-red text-bold'>{{title}}</view>
                <view class='action' @click='hideModal'>
                    <text class='cuIcon-close text-red'></text>
                </view>
            </view>
            <view class='padding-xl bg-white'>
                <slot></slot>
            </view>

            <view class="cu-bar bg-white " v-if="!customFooter">
                <view class='action margin-0 flex-sub text-green ' @click='hideModal'>
                    <view class='action margin-0 flex-sub  ' @click='onConfirm'>确定</view>
                    <view class='action margin-0 flex-sub text-gray solid-left' @click='onCancel' v-if="!hideCancel">取消</view>
                </view>
            </view>
            <slot name="footer"></slot>
            <view class="modal_close_area bg-white"></view>
        </view>
    </view>
</template>

<script>
    export default {
        name: "modal",
        data(){
            return{
                show:false
            }
        },
        created(){
            console.log(`调试:Model组件加载成功`, this.$scopedSlots);

            console.log(`调试:Slots`, this.$slots)
        },

        props:{
           title:{
               type:String,
               default:'标题'
           },
            hideCancel:{
              type:Boolean,
              default:false
            },
           value:{
               type:Boolean,
               default: false
           },
           maxWidth:{
               type:String,
               default:undefined
           },
           hideHeader:{
               type:Boolean,
               default: false
           },
           hideFooter:{
                type:Boolean,
                default: false
            }
        },
        computed:{
            customFooter(){
                return !!this.$slots.footer
            }

        },
        watch:{
            value(val){
                this.show = val
            }
        },
        methods:{
            hideModal(){
                this.show = false;
                this.$emit("input",this.show);
                this.$emit("close");
            },
            handleModalClose(){
                this.hideModal();
            },
            onConfirm(){
                this.$emit('onConfirm')
            },
            onCancel(){
                thihs.$emit('onCancel')
            }

        }
    }
</script>

<style scoped>
.modal_close_area{
    position: absolute;
    top: 550px;
}
</style>
