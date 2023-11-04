<template>
	<div class="home">
		<!-- <router-link to="/dashboard?title=登录"> -->
		<img alt="Vue logo" src="../assets/logo.png" @click="todashboard">
		<!-- </router-link> -->
		<HelloWorld msg="Welcome to Your Vue.js App" />
	</div>
</template>

<script>
	// @ is an alias to /src
	import HelloWorld from '@/components/HelloWorld.vue'

	export default {
		name: 'HomeView',
		components: {
			HelloWorld
		},
		methods: {
			todashboard() {
				// this.$router.push({
				//  path:'/dashboard',
				//  query:{
				// title:[1,2,3]
				//  }
				// })
				// this.$router.push({
				//  name:'Dashboard',
				//  params:{
				//   title:'登录'
				//  }
				// })
				this.$router.push({
						name: 'Dashboard',
						params: {
							title:(['我的','非常好',2131,{a:1,b:2}])
						}
					})
				}
			}
		}
</script>