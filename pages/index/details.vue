<template>
	<view>
		<view class="first">
			<image style="width: 220upx;height: 290upx;" src="../../static/image/3.jpg"></image>
			<view class="firRight">
				<view>
					<view style="font-size:42upx;color: #b4b4b4">万里归途</view>
					<h5 style="color: #a7a7a7;">HOME COMING</h5>
				</view>
				<view>
					<h5 style="color: #a7a7a7;">剧情 战争 IMAX DollyCiema</h5>
					<view style="color: #a7a7a7;font-size: 18upx;">2022.08.03 18:00 在中国大陆上映 137分钟</view>
				</view>
				<view class="btnBox">
					<view class="btn">想看</view>
					<view class="btn">看过</view>
				</view>
			</view>
		</view>
		<view class="second">
			<view class="secTop">
				<view style="font-size: 28upx;color: #bfbfbf;">购票评分</view>
				<view style="font-size: 24upx;color: #adadad;">319,601人想看 215,980人看过></view>
			</view>
			<view class="secBody">
				<view class="secLeft">
					<view style="text-align: end;margin: 0 20upx  0 0 ;">
						<h1 style="color: #ffb400;">9.6</h1>
						<view style="font-size: 24upx;color: #a7a7a7;">290,872人评</view>
					</view>
					<view>
						<uni-rate :readonly="true" size="2" color="#bbb" active-color="#a7a7a7" :value="5" />
						<uni-rate :readonly="true" size="5" color="#3a3a3a" active-color="#a7a7a7" :value="4" />
						<uni-rate :readonly="true" size="5" color="#3a3a3a" active-color="#a7a7a7" :value="3" />
						<uni-rate :readonly="true" size="5" color="#3a3a3a" active-color="#a7a7a7" :value="2" />
						<uni-rate :readonly="true" size="5" color="#3a3a3a" active-color="#a7a7a7" :value="1" />

					</view>
				</view>
				<view class="secRight">
					<view
						style="text-align: center;color: #ffe596;padding:6upx;background-color: #9c8c5c;border-radius: 10upx;">
						<view style="font-size: 14upx;">TOP</view>
						<view style="font-size: 24up">1</view>
					</view>
					<view style="margin:0 0 0 10upx;">
						<view style="font-size: 14upx;color: #a7a7a7;">2022年39周</view>
						<view style="font-size: 14upx;color: #b3a169;">中国大陆票房榜</view>
					</view>
				</view>
			</view>
		</view>
		<view class="third">
			<view style="color: #a7a7a7;">简介</view>

			<view>
				<view class="Express">
					<view class="info">
						<view :class="{hide:!iSinfo}">
							电影根据真实事件改编。 努米亚共和国爆发战乱，前驻地外交官宗大伟（张译 饰）与外交部新人成朗（王俊凯 饰）受命前往协助撤侨。任务顺利结束，却得知还有一批被困同胞，正在白婳（殷桃
							饰）的带领下，前往边境撤离点。情急之下，两人放弃了回家机会，逆行进入战区。赤手空拳的外交官，穿越战火和荒漠，面对反叛军的枪口，如何带领同胞走出一条回家之路……
						</view>
						<text @tap="showinfo" v-if="!iSinfo">展开</text>
					</view>
					<text @tap="showinfo" v-if="iSinfo" class="hidebtn">收起</text>
				</view>
			</view>

		</view>
		<view class="fouth">
			<view class="perform">
				<view class="performHead"> 演职人员</view>
				<scroll-view class="scroll-view_H" scroll-x="true" show-scrollbar="false">
					<view class="scroll-view-item_H">
						<view class="hotBody" @click="toDetail()">
							<view v-for="item in hotList">
								<view class="hotCard">
									<image style="height: 224upx;width: 160upx;border-radius: 20upx;" :src="item.url">
									</image>

									<view style="margin: 6upx 8upx;color: aliceblue;">{{item.name}}</view>
									<view class="butn">
										{{item.role}}
									</view>
								</view>
							</view>
						</view>

					</view>
				</scroll-view>
			</view>
		</view>
		<view class="fifth">
			<view class="hotFilm">
				<view class="hotHead">
					<view>剧照</view>
					<view style="font-size: 26upx;color: #7d7d7d;">全部44张 ></view>
				</view>
				<scroll-view class="scroll-view_H" scroll-x="true" show-scrollbar="false">
					<view class="scroll-view-item_H">
						<view class="hotBody" @click="toDetail()">
							<view v-for="item in hotList">
								<view class="hotCard">
									<image style="height:180upx;width: 280upx;border-radius: 20upx;" :src="item.url">

									</image>
								</view>
							</view>
						</view>
					</view>
				</scroll-view>
			</view>

		</view>
		<view class="sixth">
			<hb-comment ref="hbComment" @add="add" @del="del" @like="like" @focusOn="focusOn" :deleteTip="'确认删除？'"
				:cmData="commentData" v-if="commentData"></hb-comment>
		</view>
 <view style="background-color: #fff;width: 100%;text-align: center; position:fixed; bottom:0;padding: 20upx;">
	 <button  style="width: 90%;border-radius: 50upx;background-color: #e464340; color: #fff;">特惠购票</button>
 </view>


	</view>
</template>

<script>
	export default {
		data() {
			return {
				iSinfo: false,
				hotList: [{
						url: "../../static/image/1.jpg",
						name: "王逸霖",
						role: "导演"
					}, {
						url: "../../static/image/2.jpg",
						name: "万里归途",
						role: "主演"
					}, {
						url: "../../static/image/3.jpg",
						name: "明日战记",
						role: "主演"
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
				readNumer: 193,
				commentList: [{
						"id": 1, // 唯一主键
						"owner": false, // 是否是拥有者，为true则可以删除，管理员全部为true
						"hasLike": false, // 是否点赞
						"likeNum": 2, // 点赞数量
						"avatarUrl": "https://inews.gtimg.com/newsapp_ls/0/13797755537/0", // 评论者头像地址
						"nickName": "超长昵称超长...", // 评论者昵称，昵称过长请在后端截断
						"content": "啦啦啦啦", // 评论内容
						"parentId": null, // 所属评论的唯一主键
						"createTime": "2021-07-02 16:32:07" // 创建时间
					},
			  {
						"id": 2,
						"owner": false,
						"hasLike": false,
						"likeNum": 2,
						"avatarUrl": "https://inews.gtimg.com/newsapp_ls/0/13797761970/0",
						"nickName": "寂寞无敌",
						"content": "我是评论的评论",
						"parentId": 1,
						"createTime": "2021-07-02 17:05:50"
					},
					{
					            "id": 5,
					            "owner": false,
					            "hasLike": false,
					            "likeNum": 0,
					            "avatarUrl": "https://inews.gtimg.com/newsapp_ls/0/13797755537/0",
					            "nickName": "超长昵称超长...",
					            "content": "超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论超长评论",
					            "parentId": null,
					            "createTime": "2021-07-13 16:04:35"
					        },
					        {
					            "id": 13,
					            "owner": false,
					            "hasLike": false,
					            "likeNum": 0,
					            "avatarUrl": "https://inews.gtimg.com/newsapp_ls/0/13797755537/0",
					            "nickName": "超长昵称超长...",
					            "content": "@寂寞无敌 你怕不是个大聪明",
					            "parentId": 1,
					            "createTime": "2021-07-14 11:01:23"
					        }
				],
				commentData: {}
			};
		},
		onLoad() {
			this.commentData = {
				"readNumer": this.readNumer,
				"commentSize": this.commentList.length,
				"comment": this.getTree(this.commentList)
			}
		},
		methods: {
			showinfo() {
				this.iSinfo = !this.iSinfo
			},
			getTree(data) {
				let result = [];
				let map = {};
				data.forEach(item => {
					map[item.id] = item;
				});
				data.forEach(item => {
					let parent = map[item.parentId];
					if (parent) {
						(parent.children || (parent.children = [])).push(item);
					} else {
						result.push(item);
					}
				});
				return result;
			}
		}
	}
</script>

<style lang="less">
	page {
		background-color: #664d29
	}

	.first {
		padding: 10upx 20upx;
		display: flex;
		justify-content: space-between;


		.firRight {
			display: flex;
			flex-direction: column;
			justify-content: space-between;
		}

		.btnBox {
			text-align: center;
			display: flex;
			justify-content: space-around;
		}

		.btn {
			width: 220upx;
			height: 60upx;
			line-height: 60upx;
			border-radius: 10upx;
			background-color: #7a6041;
			color: #e2e2e2;
		}
	}

	.second {
		background-color: #54412c;
		padding: 20upx;
		margin: 10upx;
		border-radius: 20upx;

		.secTop {
			display: flex;
			justify-content: space-between;
		}

		.secBody {
			display: flex;
			justify-content: space-around
		}

		.secLeft {
			display: flex;

		}

		.secRight {
			display: flex;
			border: 1px solid #b49c70;
			border-radius: 20upx;
			padding: 10upx;
			margin: 8upx 0;
		}
	}

	.third {
		margin: 10upx 20upx;

		.Express {
			display: flex;
			flex-direction: column;
			padding: 20upx 30upx 0 10upx;
			position: relative;

			.info {
				display: flex;
				flex-direction: column;

				view {
					text-align: justify;
					font-size: 14px;
					color: #a7a7a7;
					;
					word-break: break-word; //换行模式
				}

				text {
					width: 70px;
					font-size: 14px;
					display: flex;
					justify-content: flex-end;
					align-items: center;
					color: #0078FF;
					position: absolute;
					bottom: 0upx;
					right: 0upx;
				}
			}

		}

		.hidebtn {
			display: flex;
			flex: 1;
			justify-content: flex-end;
			color: #0078FF;
			font-size: 14px;
		}

		.hide {
			word-break: break-word; //换行模式
			overflow: hidden;
			text-overflow: ellipsis; //修剪文字
			display: -webkit-box;
			-webkit-line-clamp: 2; //此处为上限行数
			-webkit-box-orient: vertical;
		}
	}

	.fouth {
		.perform {
			margin: 10upx 0 0 0;
			padding: 18upx;
			border-radius: 20upx;
			color: #a7a7a7;


			.performHead {
				padding: 10upx 0 20upx 0;
				color: #a7a7a7;
			}

			.hotBody {
				display: flex;
				padding: 0 10upx;
			}

			.hotCard {
				margin: 0 8upx;
				text-align: center;
				font-size: 28upx;
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
	}

	.fifth {
		.hotFilm {
			padding: 18upx;
			border-radius: 20upx;
			color: #a7a7a7;

			.hotHead {
				padding: 0 0 30upx 10upx;
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

			::-webkit-scrollbar {
				display: none;
				width: 0 !important;
				height: 0 !important;
				-webkit-appearance: none;
				background: transparent;
				color: transparent;
			}

		}
	}


	.sixth {
		background-color: #fff;
		border-radius: 20upx;
		padding: 0 20upx;
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
	
	      button {
	     
		  
	        }
</style>
