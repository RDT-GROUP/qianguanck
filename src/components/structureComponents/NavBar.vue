<template>
    <div id="NavBar">
		<div class="row">
			<div class="col-md-2"></div>
			<div class="col-md-8" style="padding-left: 40px;">
				<ul class="nav nav-pills">
					<li class="navImg"><img :src="logoTop" style="height: 50px;" align="texttop" /></li>
					<li class="navOptions" :id="tagItem.id" v-for="(tagItem, index) in navBar" :key="tagItem.index">
						<router-link :to="tagItem.url">{{tagItem.tag}}</router-link>
					</li>
				</ul>
			</div>
			<div class="col-md-2"></div>
		</div>
    </div>
</template>

<script type="text/javascript">
export default {
	data () {
		return {
			logoTop: require('../../assets/common/logo_top.jpg'),
			navBar: [{
				url: '/',
				tag: '首      页',
				id: 'p1'
			},
			{
				url: '/about',
				tag: '公司介绍',
				id: 'p2'
			},
			{
				url: '/products',
				tag: '产品中心',
				id: 'p3'
			}]
		}
	}
}

</script>

<style>
    #NavBar {
		position: fixed;
		z-index: 100000;
		background-color: white;
		width: 100%;
		height: 51px;
		border-bottom: 1px #D0D0D0 solid;
    }
	.nav > li > a {
		padding: 2px;
		padding-left: 20px;
		padding-right: 20px;
	}
	#p1 :visited {
		background-color: #FFFFFF;
	}
	#p2 :visited,
	#p3 :visited{
		background-color: #E3E3E3;
	}
	#p1 :hover,
	#p2 :hover,
	#p3 :hover{
		background-color: #E3E3E3;
		color: #000000;
	}
    .container {
        float: left;
    }
	.navImg{
		width: 330px;
		height: 50px;
		display: inline-block;
		margin-right: 20px;
		float: left;
	}
	.navOptions {
		display: inline-block;
		text-decoration: none;
		font-size: 21px;
		font-weight: 600;
		/* margin-right: 40px; */
		float: left;
		/* height: 50px; */
		white-space: pre-wrap;
		line-height: 42px;
		margin-top: 2px;
	}
	
    a:link {
        color: #686868;
		text-decoration: none;
    }
    a:visited {
        color: #686868;
        text-decoration: none;
		text-underline-color: #FF0000;
		border-bottom: 5px solid #FF0000;
    }
    a:hover {
        color: #E0E0E0;
        text-decoration: none;
    }
</style>
