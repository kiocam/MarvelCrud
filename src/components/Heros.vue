<template>
	<div class="heros">
		<div v-bind:key="hero.id" v-for="hero in heros">
			<Hero v-bind:hero="hero" />
		</div>
	</div>
</template>

<script>
import Hero from './Hero';
export default {
	name: 'Heros',
	components: {
		Hero,
	},
	props: ['heros'],
};
</script>

<style lang="scss" scoped>
.heros {
	display: flex;
	justify-content: space-between;
	align-items: baseline;
	margin-bottom: 50px;
}
</style>
