<template>
  <view class="cu-avatar bg-gray   bg-dark_gray" :class="avatarClass"   :style="'background-image: url('+src+');background-size: 100% 100%;'" ></view>
</template>

<script>
    export default {
        name: "avatar",
        props:{
            src:String,
            round:Boolean,
            radius:{
                type:[Boolean,String],
                default:'xl'
            },
            size:{
                type:String,
                default:'xl'
            }

        },
        computed:{
            avatarClass(){
                let c = this.round ?  ' round ' : this.radius ?  (this.radius === true ? `radius-xl `: `radius-${this.radius}`):'';
                c+=` padding-${this.size}`;
                console.log(`调试:计算就好的class`, c);
                return c;
            }
        },
        data() {
            return {}
        },
        methods: {}
    }
</script>

<style scoped>
  .padding-2xl {
    padding: 60upx;
  }

  .padding-3xl {
    padding: 70upx;
  }
  .padding-4xl {
    padding: 80upx;
  }
  .padding-5xl {
    padding: 90upx;
  }
  .padding-5xl {
    padding: 100upx;
  }
  .padding-6xl {
    padding: 110upx;
  }
</style>
