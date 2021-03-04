<template>
	<div>
		<Navbar />
		<router-view />
	</div>
	

</template>

<script>
import Navbar from './components/Navbar'
export default {
	components: {
		Navbar,
	},

	created() {
		// if ( this.$route.path != '/' ) {
		// 	this.$router.push('/')
		// }
	}
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Nunito:wght@900&display=swap');
</style>
