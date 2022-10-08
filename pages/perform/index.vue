<template>
	<view>
		<view>
			<view class="inv-h-w">
				<view :class="['inv-h',Inv==0?'inv-h-se':'']" @click="Inv=0">热映</view>
				<view :class="['inv-h',Inv==1?'inv-h-se':'']" @click="Inv=1">影院</view>
				<view :class="['inv-h',Inv==2?'inv-h-se':'']" @click="Inv=2">待映</view>
			</view>
			<view class="" v-show="Inv == 0">
				<image style="height: 200upx;width:100%" src="../../static/image/t0112592289f2c5b826.jpg"></image>
				<view class="card" v-for="(item,index) in lists">
					<view class="cardLeft">
						<image style="width: 150upx;height: 200upx;border-radius: 10upx;" :src="item.url">
						</image>
						<view class="cardBody">
							<view style="">
								{{item.name}}
							</view>
							<view style="font-size: 28upx;color: #868686;margin:10upx 0">
								{{item.type == 1 ? "猫眼评分"+item.score : item.personNum+'人想看'}}
							</view>
							<view style="font-size: 28upx;color: #868686;margin:6upx 0">主演：{{item.role}}</view>
							<view style="font-size: 28upx;color: #868686;">
								{{item.type ==1 ?"今天"+item.onmovie+"家影院放映"+item.onplay+"场" : item.time+"上映"}}
							</view>
						</view>
					</view>
					<view style="">
						<view class="cardRight" :style="{'background-color': item.type==1 ? '#dd4c42' : '#599ce0'} ">
							{{item.type == 1 ? "购票" : "预售"}}
						</view>
					</view>
				</view>
			</view>
			<view class="" v-show="Inv == 1">
				<view class="selectTop">
					<view>全部</view>
					<view>品牌</view>
					<view>筛选</view>
				</view>
				<view class="ticket" v-for="(items,index) in movieList">
					<view>
						<view class="first">{{items.name}}</view>
						<view class="second">{{items.local}}</view>
						<view class="third">
						<view  v-for="section in items.tip">
							<span :class="section.type===1?'note':'note1'"  style="margin:0 4upx">{{section.label}}</span>
						</view></view>
						<view class="fouth"><span class="hui">惠</span>万里归途等9部影片特惠</view>
						<view class="fifth"><span class="hui">惠</span>影院特惠促销</view>
						<view class="sixth"><span class="hui">惠</span>开卡特惠，首单1张票最高立减8.1元</view>
					</view>
					<view class="tickRight">
						<view style="color: orangered;font-size:36upx">28.9<span
								style="color: orangered;font-size: 24upx;">元</span><span
								style="font-size:24upx;color: #868686;">起</span></view>
						<view style="font-size: 26upx;color: #868686;">4.2km</view>
					</view>
				</view>
			</view>
			<view class="" v-show="Inv == 2" >	
					<view class="preFilm">
					<view style="font-size: 28upx;color: #767676;">近期最受期待</view>
						<scroll-view class="scroll-view_H" scroll-x="true" show-scrollbar="false">
							<view class="scroll-view-item_H">
								<view class="preBody">
									<view v-for="item in preList">
										<view class="preCard">
											<image style="height: 230upx;width:160upx;" :src="item.url">
												<view class="note">{{(item.wantCount)}}万想看
												</view>
											</image>
						
											<view style="margin: 14upx 8upx;">{{item.name}}</view>
											<view style="margin: 0 8upx 10upx 8upx;"  :style="{'color': item.time.length > 2 ? '#a2a0a1' : '#dd4c42'}">{{item.time}}</view>
											<!-- <view class="butn" :style="{'background-color': item.type==1 ? '#dd4c42' : '#599ce0'} ">
												{{item.type ==1 ? "购票" : "预售"}}
											</view> -->
										</view>
									</view>
								</view>
						
							</view>
						</scroll-view>
				</view>
				<view class="card" v-for="(item,index) in lists" v-show="item.type == 2">
					<view class="cardLeft">
						<image style="width: 150upx;height: 200upx;border-radius: 10upx;" :src="item.url">
						</image>
						<view class="cardBody">
							<view style="">
								{{item.name}}
							</view>
							<view style="font-size: 28upx;color: #868686;margin:10upx 0">
								{{item.type == 1 ? "猫眼评分"+item.score : item.personNum+'人想看'}}
							</view>
							<view style="font-size: 28upx;color: #868686;margin:6upx 0">主演：{{item.role}}</view>
							<view style="font-size: 28upx;color: #868686;">
								{{item.type ==1 ?"今天"+item.onmovie+"家影院放映"+item.onplay+"场" : item.time+"上映"}}
							</view>
						</view>
					</view>
					<view style="">
						<view class="cardRight"  style="background-color:#599ce0 ">
							预售
						</view>
					</view>
				</view>
			</view>
		</view>

	</view>
</template>

<script>
	export default {
		data() {
			return {
				Inv: 2,
				lists: [{
						url: "../../static/image/5.jpg",
						name: "万里归途",
						type: 1,
						score: 9.1,
						role: "张艺，玛丽，林蔡欣",
						onplay: 522,
						onmovie: 209
					},
					{
						url: "../../static/image/4.jpg",
						name: "新大头儿子小头爸爸",
						type: 2,
						personNum: 233333,
						score: 9.1,
						role: "张艺，玛丽，林蔡欣",
						time: "2022-10-23"
					},
					{
						url: "../../static/image/3.jpg",
						name: "神奇动物在哪里",
						type: 1,
						score: 9.1,
						role: "彼得·斯威福特，玛丽",
						onplay: 522,
						onmovie: 209
					}
				],
				movieList: [{
						name: "万达影城 （田浩然万科广场IMAX店）",
						local: "天河区新塘街道华观路1932号天河万科广场4层",
						tip: [{
							type: 1,
							label: "改签"
						}, {
							type: 2,
							label: "小吃"
						}, {
							type: 1,
							label: "退"
						}],
						money: 28.9,
						distance: 4.3
					},
					{
						name: "龙洞巨幕影城",
						local: "天河区新塘街道华观路1932号天河万科广场4层",
						tip: [{
							type: 1,
							label: "杜比音效"
						}, {
							type: 2,
							label: "小吃"
						}, {
							type: 1,
							label: "退"
						}],
						money: 19.9,
						distance: 4.0
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


			};
		},
		methods: {
			changeTab(Inv) {
				that.navIdx = Inv;
			},
		}
	}
</script>

<style lang="less">
	page{
		background-color: #efefef;
	}
	.inv-h-w {
		background-color: #FFFFFF;
		padding: 20upx 0;
		display: flex;
		justify-content: space-around;
	}

	.inv-h {
		font-size: 30upx;
		text-align: center;
		color: #C9C9C9;

	}

	.inv-h-se {
		color: #dd4c42;

	}

	.card {
		background-color: #fff;
		margin: 10upx  0 0 0;
		display: flex;
		padding: 24upx 20upx;
		justify-content: space-between;
		border-bottom: #dcdcdc 1upx solid;

		.cardLeft {
			display: flex;
		}

		.cardBody {
			margin: 0 20upx;
		}

		.cardRight {
			padding: 16upx 20upx;
			border-radius: 40upx;
			width: 100upx;
			text-align: center;
			color: #FFFFFF;
			margin: 50upx 0 0 0;
		}
	}

	.selectTop {
		display: flex;
		justify-content: space-around;
		color: #757575;
		font-size: 28upx;
		padding: 20upx 0;
		border: #dfdfdf 1upx solid;
	}

	.ticket {
		display: flex;
		padding: 20upx 20upx;
		justify-content: space-between;
		border: #dfdfdf 1upx solid;

		.second {
			font-size: 28upx;
			color: #757575;
			overflow: hidden; //超出的文本隐藏
			text-overflow: ellipsis; //溢出用省略号显示
			white-space: nowrap; //溢出不换行
			width: 550upx;
			margin: 10upx 0;
		}

		.third {
			display: flex;
		}

		.note {
			border-radius: 4upx;
			font-size: 24upx;
			padding: 0 10upx;
			border: 1upx solid #dd4c42;
			color: #dd4c42;
		}

		.note1 {
			border-radius: 4upx;
			font-size: 24upx;
			padding: 0 10upx;
			border: 1upx solid #00ff00;
			color: #00ff00;
		}

		.fouth,
		.fifth,
		.sixth {
			color: #888888;
			font-size: 24upx;
			margin: 10upx;

		}

		.hui {
			border-radius: 6upx;
			background-color: #ee9f00;
			color: #fff;
			padding: 0upx 6upx;
			font-size: 26upx;
			margin-right: 10upx;
		}

		.tickRight {
			text-align: end;
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
			bottom: 180upx;
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
