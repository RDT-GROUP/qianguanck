<template>
	<div id="Achievements">
		<div class="col-md-12">
			<div class="col-md-1"></div>
			<div class="col-md-10">
				<TopBlank></TopBlank>
				<div class="row" v-for="introItem in achievementIntro" :key="introItem">
					<h4 style="text-align: left;">{{introItem.content}}</h4>
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
		data() {
			return {
				achievementIntro: [{
					content: '经过近三年的发展，公司已取得多项相关技术的认证，并获得了多项发明专利以及软件著作权等各类资质认证。此外，主要项目的校准认证也已经完成并获得了校准证书。',
				},
				{
					content: '2019年9月，我司成功中标西安航空学院航空发动机实践教学创新平台项目，并于2019年12月底成功通过验收，完成交付。',
				}
				],
				
				picList: [{
					pic: require('../../assets/about/calibration1.jpg')
				},
				{
					pic: require('../../assets/about/acceptanceLetter.jpg')
				},
				{
					pic: require('../../assets/about/calibration1.jpg')
				}]
			}
		}
	}
</script>

<style scoped="true">
    img {
        transition: all 0.8s;
    }
    img:hover {
        transform: scale(1.7);
        position: sticky;
        z-index: 10;
    }
</style>
