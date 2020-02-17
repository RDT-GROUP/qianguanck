<template>
	<div id="products">
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
					<li :class="{'active': isChoosen1}" id="tab1"><a href="#" data-toggle="tab" @click="viewChanger('Product1')">超大规模实时分布式应变测量系统</a></li>
					<li :class="{'active': isChoosen2}" id="tab2"><a href="#" data-toggle="tab" @click="viewChanger('Product2')">西安航空学院静力实验平台</a></li>
				</ul>
				<component :is="currentView"></component>
			</div>
			<div class="col-md-2"></div>
		</div>
		<p>&nbsp;</p>
	</div>
</template>

<script type="text/javascript">
	import TopBlank from "./structureComponents/TopBlank.vue";
	import Product1 from "./productsSub/Product1.vue";
	import Product2 from "./productsSub/Product2.vue";
	export default {
		components: {
			TopBlank,
			Product1,
			Product2,
		},
		data () {
			return {
				pageTitle: '产品中心',
				currentView: 'Product1',
				isChoosen1: true,
				isChoosen2: false,
			}
		},
		methods: {
			viewChanger: function(component) {
				this.currentView = component;
				switch(component) {
					case 'Product1': 
						this.isChoosen1 = true;
						this.isChoosen2 = false;
						break;
					case 'Product2':
						this.isChoosen1 = false;
						this.isChoosen2 = true;
						break;
					default:
						this.isChoosen1 = true;
						this.isChoosen2 = false;
				}
			},
		}
	}
</script>

<style>
	#tab1 :visited{
		background-color: #E3E3E3;
	}
	#tab1 :hover{
		background-color: #E3E3E3;
		color: #000000;
	}
	#tab2 :visited{
		background-color: #E3E3E3;
	}
	#tab2 :hover{
		background-color: #E3E3E3;
		color: #000000;
	}
</style>
