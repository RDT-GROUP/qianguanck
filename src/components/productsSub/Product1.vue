<template>
	<div id="Product1">
		<div class="col-md-12">
			<div class="col-md-1"></div>
			<div class="col-md-10">
				<TopBlank></TopBlank>
				<div class="row">
					<h4>{{productInfo.pProfile1}}{{productInfo.pProfile2}}</h4>
				</div>
				<div class="row">
					<h4>{{productInfo.pProfile3}}</h4>
				</div>
				<TopBlank></TopBlank>
				<div class="row">
					<video id="pVideo" class="video-js vjs-big-play-centered vjs-fluid">
						<source :src="productInfo.pVideo" type="video/mp4"></source>
					</video>
				</div>
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
				productInfo: {
					pProfile1: '超大规模实时分布式应变测量系统是一种多现场总线集成的、高度模块化的超大规模实时应变测量系统。',
					pProfile2: '本系统用以解决在飞机强度、船舶设计、路桥设计等大型系统的设计中出现的大规模，甚至超大规模强度试验或检测的同步信号采集困难的问题。',
					pProfile3: '通过本系统，实验人员可以了解系统各个位置上的应力分布，进而快速找到薄弱点，进行应急处置，提高整个系统的安全性。',
					// pPic: require('../assets/products/product1/pic1.jpg'),
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
			}
		}
	}
</script>

<style>
	#Product1 {
		text-align: left;
	}
</style>
