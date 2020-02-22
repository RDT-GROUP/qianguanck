<template>
	<div id="Product1">
		<div class="col-md-12">
			<div class="col-md-1"></div>
			<div class="col-md-10">
				<TopBlank></TopBlank>
				<div class="row" v-for="(infoItem, index) in productProfile" :key="infoItem.index">
					<h4 v-html="infoItem.content"></h4>
				</div>
				<TopBlank></TopBlank>
				<div class="row">
					<video id="pVideo" class="video-js vjs-big-play-centered vjs-fluid">
						<source :src="productResource.pVideo" type="video/mp4"></source>
					</video>
				</div>
				<TopBlank></TopBlank>
				<div class="row" v-for="(introItem, index) in productIntro" :key="introItem.index">
					<h4>{{introItem.content}}</h4>
				</div>
				<TopBlank></TopBlank>
				<div class="row">
					<img class="col-md-12" style="border: #000000 1px solid;" :src="productResource.pPic1" />
				</div>
				<TopBlank></TopBlank>
				<div class="row">
					<h2 style="text-align: left;"><b>产品特点</b></h2>
				</div>
				<div class="row" v-for="(featureItem, index) in productFeature" :key="featureItem.index"><!--vue2.0 get index from array-->
					<h3><br>特点 {{index + 1}}:</h3>
					<h4 v-html="featureItem.content"></h4>	<!--this line is used to convert the varible value to html code, typically be used to implement line change.-->
					<img class="col-md-12" :src="featureItem.itemPic" />
				</div>
				<TopBlank></TopBlank>
			</div>
			<div class="col-md-1"></div>
		</div>
	</div>
</template>

<script type="text/javascript">
	import TopBlank from "../structureComponents/TopBlank.vue"
	export default {
		components: {
			TopBlank,
		},
		data () {
			return {
				productProfile: [{
					content: '<b>超大规模实时分布式应变测量系统</b>是一种多现场总线集成的、高度模块化的超大规模实时应变测量系统。' + 
							 '本系统用以解决在飞机强度、船舶设计、路桥设计等大型系统的设计中出现的大规模，甚至超大规模强度试验或检测的同步信号采集困难的问题。',
				},
				{
					content: '通过本系统，实验人员可以了解系统各个位置上的应力分布，进而快速找到薄弱点，进行应急处置，提高整个系统的安全性。',
				}],
				productIntro: [{
					content: '整套系统包括512个现场采集单元、1台CAN服务器、8块CAN管理卡、1台应用服务器、1台交换机和1套人机交互软件，其中，1台CAN服务器可支持8192个采集通道。',
				},
				{
					content: '本系统通过以太网交换机可以实现5万(50,000)测量通道以上的数据同步采集，其部分核心技术指标超过国外同类产品。',
				}],
				productFeature: [{
					content: '系统采用分布式结构，采集前端在被测点附近完成被测信号的数字化，通过CAN总线将采集数据传输至CAN服务器，再经由以太网将数据汇总在应用服务器进行' +
							 '显示和分析。采集前端距CAN服务器最远距离可达150米。<br><br>分布式结构使得采集系统的模拟线缆由原来的数十米缩短至2米，甚至更短，充分保证了测' +
							 '量精度。此外，通过对测量信号的自动编址，极大地降低了信号人工编址的工作量，提高了工作效率，也在很大程度上缩短了实验的准备时间。<br>',
				},
				{
					content: '采集前端由4个V-F测量模块及其外围电路组成，实现16路应变量的高精度测量。系统通过测试放电时间来间接得出电阻应变，芯片首先测量两个桥臂电阻的放' +
							 '电时间，根据两次放电时间的比值，计算出应变电阻的变化情况。<br>',
					itemPic: require('../../assets/products/product1/schematic.jpg'),
				},
				{
					content: '系统采用三层架构的方式，通过专用的总线间同步和总线内同步协议，解决分布式系统下大批量被测信号的同步问题，使全部采集通道实现实时同步采集。<br>',
				},
				{
					content: '系统采用多样化显示方式，提供波形显示、数据表以及云图等显示模式，可利用色彩反映应力变化并进行预警，以便于及时发现实验中的异常情况，将事后数据' +
							 '分析的实验方式变为跟踪整个实验的过程，优化实验方式。',
				}],
				productResource: {
					pPic1: require('../../assets/products/product1/systemArchitecture.jpg'),		//keep this comment to show how to invoke image resource.
					pPic2: require('../../assets/products/product1/schematic.jpg'),
					pVideo: require('../../assets/products/product1/acquisitionUnit.mp4')
				}
			}
		},
		mounted() {
			this.initVideo();
		},
		methods: {
			initVideo() {
				let myPlayer = this.$video(pVideo, {
					controls: true,
					autoplay: 'play',
					preload: "auto",
					//set the scale of the player by using width and height attributes.
					// width: "1200px",
					// height: "720px",
				});
			},
		}
	}
</script>

<style>
	#Product1 {
		text-align: left;
	}
</style>
