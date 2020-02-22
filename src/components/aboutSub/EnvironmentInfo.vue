<template>
	<div id="EnvironmentInfo">
		<div class="col-md-12">
			<div class="col-md-1"></div>
			<div class="col-md-10">
				<TopBlank></TopBlank>
				<div class="row" v-for="envItem in envIntro" :key="envItem">
					<h4 style="text-align: left;">{{envItem.content}}</h4>
				</div>
				<TopBlank></TopBlank>
				<div class="row">
					<div class="col-md-12">
						<div class="col-md-4" v-for="picItem in picList" :key="picItem"><img :src="picItem.pic" style="width: 100%;" /></div>
					</div>
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
				envIntro: [{
					content: '西安前观测控技术有限公司，创立于西北地区的核心城市，陕西省西安市。公司的办公地点位于：陕西省西安市碑林环大学创新产业带——西安创新设计中心大楼。',
				},
				{
					content: '园区内智力人才密集，科技成果汇聚，具备浓厚的创新创业氛围。附近还有西安交通大学、西北工业大学、西安电子科技大学等一流高校，人才储备丰富。',
				}],
				picList: [{
					pic: require('../../assets/about/env1.jpg')
				},
				{
					pic: require('../../assets/about/env2.jpg')
				},
				{
					pic: require('../../assets/about/env3.jpg')
				}]
			}
		}
	}
</script>

<style>
</style>
