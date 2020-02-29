<template>
	<view class="home-main">
		<uni-nav-bar class="head-nav" fixed backgroundColor="#354E44">
			<!-- 默认插槽 -->
			<view class="title">
				<text class="nav-item" :class="{active:show==1}" @tap="show=1">推荐</text>
				<text class="nav-item" :class="{active:show==2}" @tap="show=2">品牌</text>
			</view>
			<view slot="left">
				<image class="icon icon-chat" src="../../static/assets/chat.png" mode=""></image>
			</view>
			<view slot="right">
				<image class="icon icon-search" src="../../static/assets/search.png" mode=""></image>
				<image class="icon icon-cart" src="../../static/assets/cart.png" mode=""></image>
			</view>
		</uni-nav-bar>
		<!-- home 默认第一屏 -->
		<view v-show="show==1" class="section-home" >
			
			<!-- 轮播 -->
			<view class="section-banner">
				
				<swiper class="swiper-banner" indicator-active-color="#D8D8D8" :indicator-dots="true" :autoplay="true" :interval="3000"  :duration="400">
				  
					<swiper-item>
				        <view class="swipr-item">
							<image class="img" src="../../static/assets/banner1.png" mode=""></image>
						</view>
				    </swiper-item>
					
				    <swiper-item>
				        <view class="swipr-item">
				        	<image class="img" src="../../static/assets/banner1.png" mode=""></image>
				        </view>
				    </swiper-item>
					
				    <swiper-item>
				      <view class="swipr-item">
				      	<image class="img" src="../../static/assets/banner1.png" mode=""></image>
				      </view>
				    </swiper-item>
					
				</swiper>
				
				
			</view>
			
			<!-- 品牌推荐 -->
			<view class="recommended">
				<view class="p1">品牌推荐</view>
				<span class="more"><navigator url="#" hover-class="navigator-hover">更多></navigator></span>
			</view>
	
		<view class="sofa">
			<view class="back">
				<image  class="imgs" src="../../static/assets/shafa.png" mode=""></image>
				<p class="Chinese">沙发系列</p>
				<p class="English">by Adrianne</p>
			</view>
			<view class="back">
				<image  class="imgs" src="../../static/assets/muyi.png" mode=""></image>
				<p class="Chinese">木质系列</p>
				<p class="English"> by Hanna</p>
			</view>
			<view class="back">
				<image  class="imgs" src="../../static/assets/guizi.png" mode=""></image>
				<p class="Chinese">创意系列</p>
					<p class="English">by adais</p>
			</view>
		</view>
		
		<view class="recommended s">
			<view class="p1 s">特色优选</view>
			<span class="more"><navigator url="#" hover-class="navigator-hover s">更多></navigator></span>
		</view>
		
		<!-- 尾部轮播 -->
		<view class="shufflings s">
			<swiper class="swiper-banners s" indicator-active-color="#D8D8D8" previous-margin="60rpx" next-margin="60rpx">
			  
				<swiper-item>
			        <view class="swipr-items s">
						<image class="img s" src="../../static/assets/banner1.png" mode=""></image>
					<view class="commodity">
						<p class="name">现代极简吊灯</p>
						<p class="ten">by Adrianne Ho</p>
						<view class="dot">
							<view class="dot1"></view>
							<view class="dot2"></view>
							<view class="dot3"></view>
							
						</view>
						<p class="instructions">切割平整圆滑，运用漫反…</p>
					</view>
					</view>
			    </swiper-item>
				
			    <swiper-item>
			        <view class="swipr-items s">
			        	<image class="img s" src="../../static/assets/banner1.png" mode=""></image>
						<view class="commodity">
							<p class="name">现代极简吊灯</p>
							<p class="ten">by Adrianne Ho</p>
							<view class="dot">
								<view class="dot1"></view>
								<view class="dot2"></view>
								<view class="dot3"></view>
								
							</view>
							<p class="instructions">切割平整圆滑，运用漫反…</p>
						</view>
			        </view>
			    </swiper-item>
				
			    <swiper-item>
			      <view class="swipr-items s">
			      	<image class="img s" src="../../static/assets/banner1.png" mode=""></image>
					<view class="commodity">
						<p class="name">现代极简吊灯</p>
						<p class="ten">by Adrianne Ho</p>
						<view class="dot">
							<view class="dot1"></view>
							<view class="dot2"></view>
							<view class="dot3"></view>
							
						</view>
						<p class="instructions">切割平整圆滑，运用漫反…</p>
					</view>
			      </view>
			    </swiper-item>
				
			</swiper>
		</view>
		
	</view>
	
	
	
	
		<!-- home 第二瓶 -->
		<view v-show="show==2" class="section-home">
			<Brands :brandList="brandList"></Brands>
	</view>
		
	</view>
</template>

<script>
	import uniNavBar from "@/components/uni-nav-bar/uni-nav-bar.vue"
	import Brands from './barnd/index.vue'
	export default {
			components: {uniNavBar,Brands},
		data() {
			return {
				bannerList:[],
				brandList:[],
				show:1,
				
			};
			
		}
		
		
	}
</script>

<style lang="scss" scoped>
		
	
	.home-main{
		width: 750rpx;
		// height: 12034rpx;
		// height: 1170rpx;
	
		background-color:#F1ECE7;
		.title{
			width: 100%;
			display: flex;
			justify-content: center;
			.nav-item{
				font-size: 32rpx;
				color: #FFFFFF;
				letter-spacing: 2.29rpx;
				margin: 0 20rpx;
				padding-bottom: 12rpx;
				line-height: 45rpx;
					&.active{
						border-bottom: 2px solid #fff;
					}
			}
		}
		
		.icon{
			// position: relative;
			width: 42rpx;
			height: 42rpx;
			&.icon-chat{
				margin-left: 30rpx;
				}
				&.icon-search{
					margin-right: 20rpx;
				}
				&.icon-cart{
					margin-right: 10rpx;
				}
			}
			.section-home{
				height: 1170rpx;
				width: 100%;
				background-color:#F1ECE7;
	.section-banner{
		width: 750rpx;
			// width: 100%;
			// height: 426rpx;
			// background-color: pink;
			.swiper-banner{
				width: 100%;
				height: 360rpx;
				// margin-top: 30rpx;
				.swiper-item{
					width: 750rpx;
					height: 100%;
				
				}
			}
		}

		.img{
			margin: 0 auto;
			width: 750rpx;
			height: 362rpx;
			}
			
			.recommended{
				
				display: flex;
				padding-top: 30rpx;
				 .p1{
					font-size: 32rpx;
					color: #3E3E3E;
					letter-spacing: 2.29rpx;
					margin-left: 40rpx;
					}
					.more{
						width: 90rpx;
						font-size: 26rpx;
						color: #8C8C8C;
						letter-spacing: 1.86rpx;
						// p-left: 450rpx;
					
						padding-left:450rpx; ;
					}
				}
		.sofa{
				display: flex;
				  -webkit-justify-content: space-around;
				   justify-content: space-around;
				  margin-top: 39rpx;
				.back{
					width: 208rpx;
					height: 140rpx;
					background-color:#FFFFFF;
					.imgs{
					padding-top: 52rpx;
					width: 144rpx;
					height: 124rpx;
					margin: 0 auto;
					display: flex;													
				}
				.Chinese{
					width: 126rpx;
					font-size: 26rpx;
					padding-top: 40rpx;
					color: #3E3E3E;
					margin: 0 auto;
					display: flex;	
					letter-spacing: 1.86rpx;
				}
				.English{
					width: 128rpx;
					font-size: 20rpx;
					color: #B0B0B0;
					margin: 0 auto;
					display: flex;	
					letter-spacing: 1.43rpx;
				}
				}
				
			}
			
			.recommended.s{
				padding-top: 180rpx;
				
		
			}
			
		.shufflings.s{
			
			.swiper-banners.s{
				.swipr-items.s{
					width: 590rpx;
					height: 260rpx;
					background: #FFFFFF;
					box-shadow: 0 16px 48px 0 rgba(122,98,75,0.12);
					border-radius: 20px;
					border-radius: 20px;
					margin: 0 auto;
					margin-top: 50rpx;
					display: flex;
				
					.img.s{
						width: 194rpx;
						height: 280rpx;
						margin-left: 44rpx;
						
						}
					.commodity{
						margin-top: 50rpx;
						// margin-left: -36rpx;
						margin-right: 30rpx;
							.name{
								font-size: 26rpx;
								color: #3E3E3E;
								letter-spacing: 1.86rpx;
							}
							.ten{
								font-size: 18rpx;
								color: #B0B0B0;
								letter-spacing: 1.29rpx;
							}
							.dot{
								display: flex;
								margin-top: 19rpx;
								.dot1{
									width: 20rpx;
									height: 20rpx;
									border-radius:50%;
									background-color:  #446675;
									// margin-left: 20rpx;
									
								}
								.dot2{
									width: 20rpx;
									height: 20rpx;
									border-radius:50%;
									background-color:  #6A4826;
									margin: 0 10rpx;
								}
								.dot3{
									width: 20rpx;
									height: 20rpx;
									border-radius:50%;
									background-color:  #E7D8BB;
								}
							}
							.instructions{
								margin-top: 28rpx;
								font-size: 22rpx;
								
								color: #3E3E3E;
								letter-spacing: 1.57rpx;
							}
						}
				}
			}
		}
	}
}

</style>
