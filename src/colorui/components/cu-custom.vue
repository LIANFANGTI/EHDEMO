<template>
	<view>
		<view class="cu-custom" :style="[{height:CustomBar + 'px'}]">
			<view class="cu-bar fixed" :style="style"  :class="[bgImage!=''?'none-bg  bg-img':'',bgColor]">
				<view class="action" @tap="BackPage" v-if="isBack">
					<text class="cuIcon-back"></text>
					<slot name="backText"></slot>
				</view>
<!--				<view class='action' hover-class="text-green">-->
<!--					<text class='cuIcon-skinfill'></text>-->
<!--					<text class="text-df">解绑</text>-->
<!--				</view>-->
				<view class="content" :style="[{top:StatusBar + 'px'}]">
					<slot name="content"></slot>
				</view>

				<slot name="right"></slot>

			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				StatusBar: this.StatusBar,
				CustomBar: this.CustomBar
			};
		},
		name: 'cu-custom',
		computed: {
			style() {
				var StatusBar= this.StatusBar;
				var CustomBar= this.CustomBar;
				var bgImage = this.bgImage;
				var style = `height:${CustomBar}px;padding-top:${StatusBar}px;${this.titleColor ?  `color:${this.titleColor};`: ''}`;
				if (this.bgImage) {
					style = `${style}background-image:url(${bgImage});`;
				}
				if(this.bgColor){
					if(this.bgColor.indexOf("bg-") === -1){
						style  = `${style}  background-color:${this.bgColor};`
					}
				}
				return style
			}
		},
		props: {
			bgColor: {
				type: String,
				default: 'bg-white'
			},
			isBack: {
				type: [Boolean, String],
				default: false
			},
			bgImage: {
				type: String,
				default: ''
			},
			titleColor:{
				type:String,
				default:undefined
			}
		},
		methods: {
			BackPage() {
				uni.navigateBack({
					delta: 1
				});
			}
		}
	}
</script>

<style>

</style>
