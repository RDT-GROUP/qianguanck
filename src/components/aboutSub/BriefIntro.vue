<template>
	<div id="BriefIntro">
		<div class="col-md-12">
			<div class="col-md-1"></div>
			<div class="col-md-10">
				<TopBlank></TopBlank>
				<div class="row" v-for="(briefItem, index) in briefIntro" :key="briefItem.index">
					<h4 style="text-align: left;">{{briefItem.content}}</h4>
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
		data() {
			return {
				briefIntro: [{
					content: '西安前观测控技术有限公司，成立于2017年3月8日。公司主要从事“超大规模应力实时检测系统”、“高速基因比对设备”等科研工作和产业化应用实践。公司由具有多年科研开发工作经验的精干技术人员组成。',
				},
				{
					content: '公司现有员工8人，直接从事产品开发的6人。上述人员中，正高级工程师1人，工程师6人，助理工程师1人，开发人员平均年龄33岁。',
				}],
			}
		},
	}
</script>

<style>
	#BriefIntro {
		display: flex;
		flex-direction: column;
		min-height: 100%;
	}
</style>
