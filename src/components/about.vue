<template>
	<div id="about">
		<TopBlank></TopBlank>
		<div class="col-md-12">
		    <div class="col-md-2"></div>
		    <div class="col-md-8">
		        <div class="row">
		            <h1>{{pageTitle}}</h1>
		        </div>
		    </div>
		    <div class="col-md-2"></div>
		</div>
		<div class="col-md-12">
			<div class="col-md-2"></div>
			<div class="col-md-8">
				<ul class="nav nav-tabs">
					<li><p>&nbsp;&nbsp;&nbsp;</p></li>
					<li :class="{'active': isChoosen1}" id="tab1"><a href="#" data-toggle="tab" @click="viewChanger('BriefIntro')">简介</a></li>
					<li :class="{'active': isChoosen2}" id="tab2"><a href="#" data-toggle="tab" @click="viewChanger('Achievements')">公司荣誉</a></li>
					<li :class="{'active': isChoosen3}" id="tab3"><a href="#" data-toggle="tab" @click="viewChanger('EnvironmentInfo')">办公环境</a></li>
				</ul>
				<component :is="currentView"></component>
			</div>
			<div class="col-md-2"></div>
		</div>
		<p>&nbsp;</p>
	</div>
</template>

<script type="text/javascript">
import TopBlank from "./structureComponents/TopBlank.vue"
import EnvironmentInfo from "./aboutSub/EnvironmentInfo.vue"
import Achievements from "./aboutSub/Achievements.vue"
import BriefIntro from "./aboutSub/BriefIntro.vue"
export default {
	components: {
		TopBlank,
		BriefIntro,
		Achievements,
		EnvironmentInfo,
	},
	data () {
		return {
			pageTitle: '公司介绍',
			currentView: 'BriefIntro',
			isChoosen1: true,
			isChoosen2: false,
			isChoosen3: false,
		}
	},
	methods: {
		viewChanger: function(component) {
			this.currentView = component;
			switch(component) {
				case 'BriefIntro': 
					this.isChoosen1 = true;
					this.isChoosen2 = false;
					this.isChoosen3 = false;
					break;
				case 'Achievements':
					this.isChoosen1 = false;
					this.isChoosen2 = true;
					this.isChoosen3 = false;
					break;
				case 'EnvironmentInfo':
					this.isChoosen1 = false;
					this.isChoosen2 = false;
					this.isChoosen3 = true;
					break;
				// default:
				// 	this.isChoosen1 = true;
				// 	this.isChoosen2 = false;
				// 	this.isChoosen3 = false;
			}
		},
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
	/* .active {
		background-color: #E3E3E3;
		color: #000000;
		border-top-left-radius: 3px;
		border-top-right-radius: 3px;
	} */
	#tab1 :visited,
	#tab2 :visited,
	#tab3 :visited{
		background-color: #E3E3E3;
	}
	#tab1 :hover,
	#tab2 :hover,
	#tab3 :hover{
		background-color: #E3E3E3;
		color: #000000;
	}
</style>
