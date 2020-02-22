<template>
	<div id="products">
		<div class="col-md-12">
			<div class="col-md-1"></div>
			<div class="col-md-10">
				<TopBlank></TopBlank>
				<div class="row">
					<h4>{{productInfo.pProfile}}</h4>
				</div>
				<TopBlank></TopBlank>
				<div class="row">
					<img class="col-md-12" :src="productInfo.pPic" />
				</div>
			</div>
			<div class="col-md-1"></div>
		</div>
	</div>
</template>

<script>
	import TopBlank from "../structureComponents/TopBlank.vue"
	export default {
		components: {
			TopBlank,
		},
		data () {
			return {
				pageTitle: '产品中心',
				productInfo: {
					pTitle: '西安航空学院静力试验平台',
					pProfile: '我司于2019年下半年为西安航空学院提供一套航空部件静力试验教学平台。',
					pPic: require('../../assets/products/product2/pic1.jpg'),
					// pVideo: require('../assets/products/product2/acquisitionUnit.mp4')
				}
			}
		}
	}
</script>

<style>
</style>
