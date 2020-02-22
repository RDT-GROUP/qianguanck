<template>
	<div id="app">
		<NavBar/>
		<!-- <Billboard/> -->
		<!-- <router-view/> -->
		<div :style="{minHeight: Height+'px'}"><router-view></router-view></div>
		<Footer></Footer>
	</div>
</template>

<script>
import NavBar from './components/structureComponents/NavBar.vue'
// import Billboard from './components/structureComponents/Billboard.vue'
import Footer from './components/structureComponents/Footer.vue'
export default {
	components: {
		NavBar,
		// Billboard,
		Footer
	},
	data() {
		return {
			Height: 0,
		}
	},
	mounted() {
		this.Height = document.documentElement.clientHeight - 170;
		window.onresize = ()=> {this.Height = document.documentElement.clientHeight -170};
	},
}
</script>

<style>
body {
    margin: 0px;
	/* background-image: url(./assets/common/backgroundImg.jpg);
	background-size: cover;
	background-position: center; */
}
body::-webkit-scrollbar {
    width: 0px;
}
hr {
    background-color: #D0D0D0;
    height: 1px;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
