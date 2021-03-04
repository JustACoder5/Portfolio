<template>
	<vs-navbar shadow v-model='active' class='nav'>
		<template #left>
			<router-link to='/' style='text-decoration: none;' @click.native='removeHLine'><h1 class='navbar-brand'>News.</h1></router-link>
		</template>

		<template #right>
			<div class="navbar-items">
			
			<vs-navbar-item :active="active == 'about'"
							id='about' 
							class='n-item'
							to='/about'>
				about
			</vs-navbar-item>

			<vs-navbar-item :active="active == 'contact'"
							id='contact' 
							to='/contact'
							class='n-item'>
				contact
			</vs-navbar-item>
		</div>
		</template>
		
		
		
	</vs-navbar>
</template>

<script>
export default {
	data() {
		return {
			active: 'guide',
			underline: document.getElementsByClassName('vs-navbar__line')
		}
	},
	methods: {
		removeHLine() {
			console.log(this.$el.children[0].children[2].children[0])
			// if ( this.$el.children[0].children[2].children[0].children[0].classList)
			if ( this.$el.children[0].children[2].children[0].children[0].classList[2] == 'active' ) {
				this.$el.children[0].children[2].children[0].children[0].classList.remove('active')
				this.underline[0].style.display = 'none'
			} else if ( this.$el.children[0].children[2].children[0].children[1].classList[2] == 'active' ) {
				this.$el.children[0].children[2].children[0].children[1].classList.remove('active')
				this.underline[0].style.display = 'none'

				document.getElementsByClassName('n-item')[0].addEventListener('click', () => {
					this.underline[0].style.display = 'block'
				})
				document.getElementsByClassName('n-item')[1].addEventListener('click', () => {
					this.underline[0].style.display = 'block'
					
				})
			}

		
		}
	}
}
</script>

<style>

.navbar-brand {
	position: relative;
	left: 55px;
	font-size: 50px;
	letter-spacing: 5px;
	margin: 5px !important;
	color: #2C3E50;

}


.n-item {
	padding-left: 65px !important;
	padding-right: 65px !important;
	font-size: 25px !important;
	letter-spacing: 2px;
	
	
}

.nav { 
	font-family: 'Nunito', sans-serif;
}

</style>