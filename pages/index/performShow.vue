<template>
	<view>

		<view class="discount">
			<scroll-view class="scroll-view_H" scroll-x="true" show-scrollbar="false">
				<view class="scroll-view-item_H">
					<view class="menubox">
						<image src="../../static/image/a.png"
							style="width:120upx ;height:120upx;padding: 14upx;border-radius: 26upx;" mode=""></image>
						<view class="text">电影/影院</view>
					</view>
				</view>
				<view class="scroll-view-item_H">
					<view class="menubox">
						<image src="../../static/image/b.png"
							style="width:120upx ;height:120upx;padding: 14upx;border-radius: 26upx;" mode=""></image>
						<view class="text">脱口秀</view>
					</view>
				</view>
				<view class="scroll-view-item_H">
					<view class="menubox">
						<image src="../../static/image/c.png"
							style="width:120upx ;height:120upx;padding: 14upx;border-radius: 26upx;" mode=""></image>
						<view class="text">休闲展览</view>
					</view>
				</view>
				<view class="scroll-view-item_H">
					<view class="menubox">
						<image src="../../static/image/d.png"
							style="width:120upx ;height:120upx;padding: 14upx;border-radius: 26upx;" mode=""></image>
						<view class="text">电影/影院</view>
					</view>
				</view>
				<view class="scroll-view-item_H">
					<view class="menubox">
						<image src="../../static/image/e.png"
							style="width:120upx ;height:120upx;padding: 14upx;border-radius: 26upx;" mode=""></image>
						<view class="text">电影/影院</view>
					</view>
				</view>
				<view class="scroll-view-item_H">
					<view class="menubox">
						<image src="../../static/image/a.png"
							style="width:120upx ;height:120upx;padding: 14upx;border-radius: 26upx;" mode=""></image>
						<view class="text">电影/影院</view>
					</view>
				</view>
			</scroll-view>
		</view>

		<view class="hotFilm">
			<view class="hotHead">
				<image style="width: 180upx;height: 48upx;" src="../../static/image/today-look.png"></image>
				<view style="font-size: 26upx;color: #7d7d7d;">更多></view>
			</view>
			<scroll-view class="scroll-view_H" scroll-x="true" show-scrollbar="false">
				<view class="scroll-view-item_H">
					<view class="hotBody" @click="toDetail()">
						<view v-for="item in hotList">
							<view class="hotCard">
								<image style="height: 220upx;width: 160upx;border-radius: 20upx;" :src="item.url">
								</image>
								<view class="butn">
									{{item.note}}
								</view>
								<view style="margin: 14upx 8upx;">{{item.name}}</view>

							</view>
						</view>
					</view>

				</view>
			</scroll-view>
		</view>

		<view style="margin: 0 20upx;border-radius: 10upx;">
			<swiper :indicator-dots="true" :autoplay="true" :interval="3000" :duration="1000" class="calsur">
				<swiper-item>
					<image src="../../static/image/f.jpg" class="calsur"></image>
				</swiper-item>
				<swiper-item>
					<image src="../../static/image/g.jpg" class="calsur"></image>
				</swiper-item>
			</swiper>
		</view>

		<view class="hotFilm">
			<view class="hotHead">
				<view>七日精选 | 阅读看点</view>
				<view style="font-size: 26upx;color: #7d7d7d;">更多></view>
			</view>
			<scroll-view class="scroll-view_H" scroll-x="true" show-scrollbar="false">
				<view class="scroll-view-item_H">
					<view class="hotBody" @click="toDetail()">
						<view v-for="item in hotList">
							<view class="hotCard">
								<image style="height: 220upx;width: 160upx;border-radius: 20upx;" :src="item.url">
								</image>
								<view style="margin: 14upx 8upx;">{{item.name}}</view>
								<view style="color: red;">
									￥{{item.price}}<span style="color: #7d7d7d;font-size: 24upx;">起</span>
								</view>
							</view>
						</view>
					</view>

				</view>
			</scroll-view>
		</view>


		<view class="perform">
			<view style="margin:  0 20upx;">大咖新动态</view>
			<scroll-view class="scroll-view_H" scroll-x="true" show-scrollbar="false">
				<view class="scroll-view-item_H">
					<view class="discount">
						<view v-for="(item,index) in  personList">
							<view class="menubox">
								<image :src="item.url"
									style="width:120upx ;height:120upx;padding: 14upx;border-radius: 50%;" mode="">
								</image>
								<view style="">{{item.name}}</view>
								<view class="text">{{item.role}}</view>
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
				hotList: [{
						url: "../../static/image/1.jpg",
						name: "哥，你好",
						note: "火热抢购中",
						score: 9.0,
						price: 80
					}, {
						url: "../../static/image/2.jpg",
						name: "万里归途",
						note: "即将开抢",
						score: 0,
						price: 80
					}, {
						url: "../../static/image/3.jpg",
						name: "明日战记",
						note: "火热抢购中",
						score: 9.0,
						price: 80
					},
					{
						url: "../../static/image/3.jpg",
						name: "明日战记",
						note: "火热抢购中",
						score: 9.0,
						price: 90
					}
				],
				personList: [{
						url: "../../static/image/1.jpg",
						name: "王逸霖",
						role: "导演"
					}, {
						url: "../../static/image/2.jpg",
						name: "胡一八",
						role: "主演"
					}, {
						url: "../../static/image/3.jpg",
						name: "尼克",
						role: "主演"
					},
					{
						url: "../../static/image/3.jpg",
						name: "小hi里",
						role: "友情出演"
					},
					{
						url: "../../static/image/3.jpg",
						name: "明日战记",
						role: "友情出演"
					},
					{
						url: "../../static/image/3.jpg",
						name: "明日战记",
						role: "友情出演"
					}
				],
			};
		}
	}
</script>

<style lang="less">
	.discount {
		display: flex;
		justify-content: space-around;
		padding: 10upx 20upx;
		background-color: #ffffff;

		.menubox {
			text-align: center;
		}

		.text {
			font-size: 24upx;
			color: #868686;
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

		.butn {
			padding: 4upx;
			border-radius: 10upx;
			text-align: center;
			margin: 10upx 0;
			background: linear-gradient(135deg, #ff7142, #ff0b0b);
			color: #fff;
			font-size: 20upx;
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



	.calsur {
		width: 100%;
		height: 120upx;
		border-radius: 10upx;
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
