<template>
	<view class="content">
		<!-- 搜索框 -->
		<uni-search-bar @confirm="search" :focus="true" v-model="searchValue" @input="input" @cancel="cancel"
			@clear="clear">
		</uni-search-bar>
		<!-- 轮播图 -->
		<swiper :indicator-dots="true" :autoplay="true" :interval="3000" :duration="1000" class="calsur">
			<swiper-item>
				<image src="../../static/image/t0112592289f2c5b826.jpg" class="calsur"></image>
			</swiper-item>
			<swiper-item>
				<image src="../../static/image/t018f5d1782056a4cb5.jpg" class="calsur"></image>
			</swiper-item>
		</swiper>
		<!-- 菜单栏 -->
		<view class="menu">
			<view class="menubox">
				<image src="../../static/image/movie.png"
					style="width:80upx ;height:80upx;background-image: linear-gradient(to bottom right, #ee8663, #ffcc65);padding: 14upx;border-radius: 26upx;"
					mode=""></image>
				<view class="text">电影/影院</view>
			</view>
			<view class="menubox">
				<image src="../../static/image/music.png"
					style="width:80upx ;height:80upx;background-image: linear-gradient(to bottom right,  #7f33f4, #d977ff);padding: 14upx;border-radius: 26upx;"
					mode=""></image>
				<view class="text">演出/玩乐</view>
			</view>
			<view class="menubox">
				<image src="../../static/image/hall.png"
					style="width:80upx ;height:80upx;background-image: linear-gradient(to bottom right,  #ec5a4a, #ff926d);padding: 14upx;border-radius: 26upx;"
					mode=""></image>
				<view class="text">放映厅</view>
			</view>
			<view class="menubox">
				<image src="../../static/image/joy.png"
					style="width:80upx ;height:80upx;background-image: linear-gradient(to bottom right,  #eb4e56, #ff77b7);padding: 14upx;border-radius: 26upx;"
					mode=""></image>
				<view class="text">脱口秀</view>
			</view>
		</view>
		<!-- 优惠活动 -->
		<view class="discount">
			<scroll-view class="scroll-view_H" scroll-x="true" show-scrollbar="false">
				<view class="scroll-view-item_H">
					<view class="card">
						<view style="font-weight:600 ;">立减50元</view>
						<view style="font-size: 24upx;margin-top:5upx ;color: #7d7d7d;">哥，你好</view>
					</view>
				</view>
				<view class="scroll-view-item_H">
					<view class="card">
						<view style="font-weight:600 ;">拼团立减</view>
						<view style="font-size: 24upx;margin-top:5upx ;color: #7d7d7d;">大头儿子</view>
					</view>
				</view>
				<view class="scroll-view-item_H">
					<view class="card">
						<view style="font-weight:600 ;">影展周边</view>
						<view style="font-size: 24upx;margin-top:5upx ;color: #7d7d7d;">显示促销</view>
					</view>
				</view>
				<view class="scroll-view-item_H">
					<view class="card">
						<view style="font-weight:600 ;">抢百元券</view>
						<view style="font-size: 24upx;margin-top:5upx ;color: #7d7d7d;">特别演出</view>
					</view>
				</view>
				<view class="scroll-view-item_H">
					<view class="card">
						<view style="font-weight:600 ;">抢百元券</view>
						<view style="font-size: 24upx;margin-top:5upx ;color: #7d7d7d;">特别演出</view>
					</view>
				</view>
			</scroll-view>
		</view>

		<!-- 正在上映 -->
		<view class="hotFilm">
			<view class="hotHead">
				<view>正在上映</view>
				<view style="font-size: 26upx;color: #7d7d7d;">全部44部 ></view>
			</view>

			<scroll-view class="scroll-view_H" scroll-x="true" show-scrollbar="false">
				<view class="scroll-view-item_H">
					<view class="hotBody">
						<view v-for="item in hotList">
							<view class="hotCard">
								<image style="height: 310upx;width: 220upx;border-radius: 20upx;" :src="item.url">
									<view class="note">{{ item.score == 0.0?  "暂无评分" :(item.score).toFixed(1)+"分" }}
									</view>
								</image>

								<view style="margin: 14upx 8upx;">{{item.name}}</view>
								<view class="butn" :style="{'background-color': item.type==1 ? '#dd4c42' : '#599ce0'} ">
									{{item.type ==1 ? "购票" : "预售"}}
								</view>
							</view>
						</view>
					</view>

				</view>
			</scroll-view>
		</view>

		<!-- 待映推荐 -->
		<view class="preFilm">
			<view class="preHead">
				<view>待映推荐 | 即将上映</view>
				<view style="font-size: 26upx;color: #7d7d7d;">全部19部 ></view>
			</view>
			<scroll-view class="scroll-view_H" scroll-x="true" show-scrollbar="false">
				<view class="scroll-view-item_H">
					<view class="preBody">
						<view v-for="item in preList">
							<view class="preCard">
								<image style="height: 310upx;width: 220upx;border-radius: 20upx;" :src="item.url">
									<view class="note">{{(item.wantCount)}}万想看
									</view>
								</image>
			
								<view style="margin: 14upx 8upx;">{{item.name}}</view>
								<view style="margin: 0 8upx 10upx 8upx;"  :style="{'color': item.time.length > 2 ? '#a2a0a1' : '#dd4c42'}">{{item.time}}</view>
								<view class="butn" :style="{'background-color': item.type==1 ? '#dd4c42' : '#599ce0'} ">
									{{item.type ==1 ? "购票" : "预售"}}
								</view>
							</view>
						</view>
					</view>
			
				</view>
			</scroll-view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
				searchValue: '',
				hotList: [{
						url: "../../static/image/1.jpg",
						name: "哥，你好",
						type: 1,
						score: 9.0
					}, {
						url: "../../static/image/2.jpg",
						name: "万里归途",
						type: 2,
						score: 0
					}, {
						url: "../../static/image/3.jpg",
						name: "明日战记",
						type: 1,
						score: 9.0
					},
					{
						url: "../../static/image/3.jpg",
						name: "明日战记",
						type: 1,
						score: 9.0
					}
				],
				preList: [{
						url: "../../static/image/1.jpg",
						name: "哥，你好",
						type: 2,
						time:'明天',
						wantCount: 3.0
					}, {
						url: "../../static/image/2.jpg",
						name: "万里归途",
						type: 2,
						time:'后天',
						wantCount:2.6
					}, {
						url: "../../static/image/3.jpg",
						name: "明日战记",
						type: 2,
						time:'明天',
						wantCount: 12.0
					},
					{
						url: "../../static/image/3.jpg",
						name: "明日战记",
						time:'10月3号',
						type: 2,
						wantCount: 1.5
					}
				]
			}
		},
		onLoad() {

		},
		filters:{
				//取截单元,单位
				moneyFormat:function(arg){
				if(arg.toString().length>=9){
						const moneys = arg/100000000
						const realVal = parseFloat(moneys).toFixed(2);
						return realVal+"亿"
					}else if(arg.toString().length>=4){
						const moneys = arg/10000
						const realVal = parseFloat(moneys).toFixed(2);
						return realVal+"万"
					}
					}
				},
		methods: {

		}
	}
</script>

<style lang="less">
	page {
		background-color: #efefef;
	}

	.content {
		padding: 0 20upx;
	}

	.calsur {
		width: 100%;
		height: 320upx
	}

	.menu {
		display: flex;
		justify-content: space-around;
		padding: 20upx;
		margin: 10upx 0;
		background-color: #ffffff;
		border-radius: 20upx;

		.menubox {
			text-align: center;
		}

		.text {
			font-size: 22upx;
			color: #868686;
		}
	}

	.discount {
		background-color: #fff;
		display: flex;
		padding: 20upx 0;
		border-radius: 20upx;




		.card {

			border: solid 1upx #cacaca;
			border-radius: 16upx;
			margin: 0 8upx;
			padding: 16upx;
		}
		
		::-webkit-scrollbar {
			display: none;
			width: 0 !important;
			height: 0 !important;
			-webkit-appearance: none;
			background: transparent;
			color: transparent;
		}

	
	}

	.hotFilm {
		margin: 10upx 0;
		padding: 18upx;
		background-color: #fff;
		border-radius: 20upx;

		.hotHead {
			padding: 10upx 20upx 20upx 20upx;
			display: flex;
			justify-content: space-between;
			align-items: flex-end
		}

		.hotBody {
			display: flex;
			padding: 0 10upx;
		}

		.hotCard {
			margin: 0 8upx;
		}

		.note {
			position: absolute;
			/*设为绝对定位*/
			bottom: 160upx;
			margin: 0 20upx;
			color: #f7df85;
			background: rgba(0, 0, 0, 0.4);

		}

		.butn {
			padding: 10upx;
			border-radius: 50upx;
			width: 120upx;
			text-align: center;
			margin: 10upx 0;
			color: #fff;
		}
		
		::-webkit-scrollbar {
			display: none;
			width: 0 !important;
			height: 0 !important;
			-webkit-appearance: none;
			background: transparent;
			color: transparent;
		}

	}

	.preFilm {
		background-color: #fff;
		border-radius: 20upx;
		padding: 20upx;
		
		.preHead{
			display: flex;
			justify-content: space-between;
			padding: 10upx;
		}
		.preBody {
			display: flex;
		
		}
		
		.preCard {
			margin: 20upx 8upx;
		}
		
		.note {
			position: absolute;
			/*设为绝对定位*/
			bottom: 226upx;
			margin: 0 10upx;
			font-size: 28upx;
			color: #fff;
			background: rgba(0, 0, 0, 0.4);
		
		}
		
		.butn {
			padding: 10upx;
			border-radius: 50upx;
			width: 120upx;
			text-align: center;
			margin: 10upx 0;
			color: #fff;
		}
		
		::-webkit-scrollbar {
			display: none;
			width: 0 !important;
			height: 0 !important;
			-webkit-appearance: none;
			background: transparent;
			color: transparent;
		}
	}
	
	
	.scroll-view_H {
		white-space: nowrap;
		width: 100%;
	}
	
	.scroll-view-item_H {
		display: inline-block;
	
	}
	
	::-webkit-scrollbar {
		display: none;
		width: 0 !important;
		height: 0 !important;
		-webkit-appearance: none;
		background: transparent;
		color: transparent;
	}
</style>
