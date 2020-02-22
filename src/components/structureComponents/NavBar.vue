<template>
    <div id="NavBar">
		<div class="row">
			<div class="col-md-2"></div>
			<div class="col-md-8" style="padding-left: 5px;">
				<ul>
					<li class="navImg"><img :src="logoTop" style="height: 50px;" align="texttop" /></li>
					<li class="navOptions" v-for="(tagItem, index) in navBar" :key="tagItem.index">
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
				tag: '首      页'
			},
			{
				url: '/about',
				tag: '公司介绍'
			},
			{
				url: '/products',
				tag: '产品中心'
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
    .container {
        float: left;
    }
    /* .container > div {
        display: inline;
        text-decoration: none;
        font-size: 18px;
        font-weight: 800;
        margin-left: 40px;
        white-space: pre-wrap;
    } */
	.navImg{
		width: 330px;
		height: 50px;
		display: inline-block;
		margin-right: 40px;
		float: left;
	}
	.navOptions {
		display: inline-block;
		text-decoration: none;
		font-size: 21px;
		font-weight: 600;
		margin-right: 40px;
		float: left;
		height: 50px;
		white-space: pre-wrap;
		line-height: 42px;
		margin-top: 3px;
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
