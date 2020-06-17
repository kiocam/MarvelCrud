<template>
	<header>
		<router-link to="/">
			<img
				class="logo"
				alt="Vue logo"
				src="../../assets/FAVPNG_lego-marvels-avengers-hulk-youtube-logo_nHMjVyE4.png"
			/>
		</router-link>
		<nav>
			<ul>
				<!-- <li>
					<router-link to="About">Iron-Man</router-link>
				</li>
				
				<li>
					<router-link to="About">Cpt-America</router-link>
				</li>
				
				<li>
					<router-link to="About">Thor</router-link>
				</li>
			
				<li>
					<router-link to="About">Hulk</router-link>
				</li> -->
			</ul>
		</nav>
		<button>
			<AddHero />
		</button>
	</header>
</template>

<script>
import AddHero from '../AddHero';
export default {
	name: 'Header',

	components: {
		AddHero,
	},
};
</script>

<style lang="scss" scoped>
header {
	display: flex;
	justify-content: space-between;
	align-items: center;
	padding: 25px 50px;
	color: #fff;
	font-size: 25px;
	background: #000;

	.logo {
		width: 360px;
		cursor: pointer;
		opacity: 0.9;
	}
	li,
	a {
		display: inline-block;
		text-decoration: none;
		color: #fff;
	}

	li a {
		padding: 0px 20px;
	}

	.btn {
		width: 150px;
		padding: 10px 20px;
		background: transparent;
		border: 2px solid #efef;
		border-radius: 2px;
		font-size: 0.6em;
		font-weight: bold;
	}
}
</style>
