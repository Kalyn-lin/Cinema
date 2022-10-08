<template>
	<view class="content">
		<!-- 第一部分 -->
		<view class="first">
			<view class="firstLeft">
				<image style="width: 120upx;height: 120upx;border-radius: 50%;" :src="info.url"></image>
				<view class="firstMid">
					<view style="font-size: 36upx;">{{info.name}}</view>
					<view style="font-size: 26upx;color: #7f7f7f;">成长值 {{info.grade}} ></view>
					<progress percent="40%" stroke-width="1" activeColor="#dd4c42" />
				</view>
			</view>
			<view class="firstRight">
				<view class="btn">个人主页></view>
			</view>
		</view>
		<!-- 第二部分 -->
		<view class="second">
			<view class="secondLeft">
				<view><span style="font-size: 42upx;vertical-algin:bottom;margin: 0 5upx 0 0;">1 </span> 想看</view>
				<view style="color: #b3b3b3;">></view>
			</view>
			<view style="border: #d6d6d6 solid 1upx;margin: 0 10upx"></view>
			<view class="secondRight">
				<view><span style="font-size: 42upx;vertical-algin:bottom;margin: 0 5upx 0 0">3 </span> 看过</view>
				<view style="color: #b3b3b3;">></view>
			</view>
		</view>
		<!-- 第三部分 -->
		<view class="third">
			<view class="thirdTop">我的订单</view>
			<view class="thirdBody">
				<view>
					<image style="width: 90upx;height:90upx" src="../../static/icon/film-select.png"></image>
					<view class="note">电影票</view>
				</view>
				<view>
					<image style="width: 90upx;height:90upx" src="../../static/icon/film-select.png"></image>
					<view class="note">演出票</view>
				</view>
				<view>
					<image style="width: 90upx;height:90upx" src="../../static/icon/film-select.png"></image>
					<view class="note">在线影院</view>
				</view>
				<view>
					<image style="width: 90upx;height:90upx" src="../../static/icon/film-select.png"></image>
					<view class="note">周边</view>
				</view>
			</view>
		</view>
		<!-- 第四部分 -->
		<view class="fouth">
			<view class="fouthTop">
				<view class="fouthCard">
					<view style="margin-bottom: 16upx;">优惠券</view>
					<view style="color: #626262;">1张可用</view>
				</view>
				<view class="fouthCard">
					<view style="margin-bottom: 16upx;">折扣卡</view>
					<view style="color: #626262;">0张可用</view>
				</view>
				<view class="fouthCard">
					<view style="margin-bottom: 16upx;">猫享卡</view>
					<view style="color: #626262;">去办卡</view>
				</view>
				<view class="fouthCard">
					<view style="margin-bottom: 16upx;">喵币</view>
					<view style="color: #626262;">0</view>
				</view>
			</view>
			<view class="fouthBtn">
				<view class="btnLeft">
					<image style="height: 30upx;width: 30upx;vertical-align: bottom;" src="../../static/icon/film.png"></image>
					<view style="margin: 0 14upx;">
						万里归途
					</view>
					<view><span style="color: #cf0000;">3元</span>电影代金卷已到账</view>
				</view>
				<view>></view>
			</view>
		</view>
		<!-- 第五部分 -->
		<view style="font-size: 28upx;color: #626262;margin:20upx 20upx;">精选服务</view>
		<view class="fifth">
			<view class="fifthCard">
				<view style="margin: 0 0 20upx  0;">省钱月卡</view>
				<view class="fifthBtn">
					<view class="fifthLeft">
						<view style="margin: 10upx 0 10upx 0;">双向礼遇 购票立减</view>
						<view style="font-size: 24upx;color: #7f7f7f;">点击省钱</view>
						</view>
					<image style="width: 110upx;height: 110upx;border-radius: 10upx;" src="../../static/image/1.jpg"></image>
				</view>
			</view>
			<view class="fifthCard">
				<view style="margin: 0 0 20upx  0;">省钱月卡</view>
				<view class="fifthBtn">
					<view class="fifthLeft">
						<view style="margin: 10upx 0 10upx 0;">双向礼遇 购票立减</view>
						<view style="font-size: 24upx;color: #7f7f7f;">点击省钱</view>
						</view>
					<image style="width: 120upx;height: 120upx;border-radius: 10upx;" src="../../static/image/1.jpg"></image>
				</view>
			</view>
			<view class="fifthCard">
				<view style="margin: 0 0 20upx  0;">省钱月卡</view>
				<view class="fifthBtn">
					<view class="fifthLeft">
						<view style="margin: 10upx 0 10upx 0;">双向礼遇 购票立减</view>
						<view style="font-size: 24upx;color: #7f7f7f;">点击省钱</view>
						</view>
					<image style="width: 120upx;height: 120upx;border-radius: 10upx;" src="../../static/image/1.jpg"></image>
				</view>
			</view>
			<view class="fifthCard">
				<view style="margin: 0 0 20upx  0;">省钱月卡</view>
				<view class="fifthBtn">
					<view class="fifthLeft">
						<view style="margin: 10upx 0 10upx 0;">双向礼遇 购票立减</view>
						<view style="font-size: 24upx;color: #7f7f7f;">点击省钱</view>
						</view>
					<image style="width: 120upx;height: 120upx;border-radius: 10upx;" src="../../static/image/1.jpg"></image>
				</view>
			</view>
		</view>
		<!-- 第六部分 -->
		<view style="font-size: 28upx;color: #626262;margin:20upx 20upx;">更多服务</view>
		<view class="sixth">
			<view class="sixthCard">
				<image style="height: 50upx;width: 50upx;border-radius: 50%;margin: 0 0 10upx 0;" src="../../static/logo.png"></image>
				<view style="font-size: 26upx;color: #626262;">关注公众号</view>
			</view>
			<view class="sixthCard">
				<image style="height: 50upx;width: 50upx;border-radius: 50%;margin: 0 0 10upx 0;" src="../../static/logo.png"></image>
				<view style="font-size: 26upx;color: #626262;">新片上映</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				info: {
					url: "../../static/image/filename.jpeg",
					name: "我",
					grade: "5/30"
				}
			};
		}
	}
</script>

<style lang="less">
	page {
		background-color: #efefef;
	}

	.content {
		// padding: 20upx  ;
	}

	.first {
		display: flex;
		justify-content: space-between;
		padding: 40upx 10upx 30upx 30upx;
		background-image: linear-gradient(to bottom, #ffd4be, #fffcf6);


		.firstLeft {
			display: flex;
		}

		.firstMid {
			display: flex;
			flex-direction: column;
			justify-content: space-around;
			margin: 0 20upx;
		}

		.firstRight {
			vertical-align: center;
			margin-top: 20upx
		}

		.btn {
			background-image: linear-gradient(to left, #ffe1cf, #fffaf2);
			padding: 14upx 20upx;
			border-radius: 30upx 0 0 30upx;
			font-size: 28upx;
			color: #8c8c8c
		}
	}

	.second {
		display: flex;
		background-color: #fff;
		border-radius: 20upx;
		justify-content: space-between;
		margin: 0 10upx;
		padding: 24upx 20upx;

		.secondLeft {
			display: flex;
			justify-content: space-between;
			width: 50%;
			margin: 0 10upx;
			vertical-algin: bottom
		}

		.secondRight {
			display: flex;
			justify-content: space-between;
			width: 50%;

		}
	}

	.third {
		margin: 20upx 10upx;
		background-color: #fff;
		border-radius: 20upx;
		padding:20upx;
		

		.thirdTop {
			padding: 0 10upx;
		}

		.thirdBody {
			display: flex;
			justify-content: space-around;
			text-align: center;
			margin: 30upx 0upx 10upx 0;
		}
		.note{
			font-size: 28upx;
			color: #787878;
		}
	}

.fouth{
	margin: 20upx 10upx;
	background-color: #fff;
	border-radius: 20upx;
	padding:30upx 20upx;
	text-align: center;
	
	.fouthTop{
		display: flex;
		justify-content: space-around;
	}
	
	.fouthBtn{
		display: flex;
		justify-content: space-between;
		margin: 26upx 0 0 0 ;
		background-image:linear-gradient(to right, #ffece0,#fff);
		padding: 16upx 10upx 6upx 10upx ;
		border-radius: 20upx;
	}
	
	.btnLeft{
		display:flex;
		color: #787878;
		font-size: 24upx;
		margin: 0 10upx;
	}
}

.fifth{
	margin: 20upx 10upx;
	display: flex;
	justify-content: space-between;
	flex-wrap: wrap;
	
	.fifthCard{
		background-color: #fff;
		border-radius: 20upx;
		padding: 20upx;
		margin: 10upx 10upx;
		width: 300upx;
	}
	.fifthBtn{
		display: flex;
	}
	.fifthLeft{
		font-size: 28upx;
		color: #444444;
	
	}
}
.sixth{
	margin: 20upx 10upx;
	background-color: #fff;
	border-radius: 20upx;
	padding:40upx 20upx;
	display: flex;
	
	.sixthCard{
	margin:0 30upx;
	text-align: center;
	}
}

</style>
