<template>
	<div class="home">
		<Header />
		<CallToAction />
		<Heros v-bind:heros="heros" v-on:new-hero="addHero" />
		<Footer />
	</div>
</template>

<script>
import Header from '../components/layout/Header';
import CallToAction from '../components/layout/CallToAction';
import Heros from '../components/Heros';
import Footer from '../components/layout/Footer';
import axios from 'axios';

export default {
	name: 'Home',
	components: {
		Header,
		CallToAction,
		Heros,
		Footer,
	},

	data() {
		return {
			heros: [],
		};
	},

	created() {
		axios
			.get('http://192.168.2.12:3000/heros')
			.then((res) => (this.heros = res.data))
			.catch((err) => console.log(err));
	},

	methods: {
		addHero(hero) {
			const {
				name,
				powerstats: {
					intelligence,
					strength,
					speed,
					durability,
					power,
					combat,
				},
				image,
				bio,
			} = hero;

			axios
				.post('http://192.168.2.12:3000/heros', {
					name,
					intelligence,
					strength,
					speed,
					durability,
					power,
					combat,
					image,
					bio,
				})
				.then((res) => (this.heros = [...this.heros, res.data]))
				.catch((err) => console.log(err));
		},
	},
};
</script>

<style lang="scss">
p {
	color: #000;
}
</style>
