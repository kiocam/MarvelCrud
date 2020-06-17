<template>
	<div class="text-center">
		<v-dialog v-model="dialog" width="500">
			<template v-slot:activator="{ on }">
				<v-btn outlined color="white" dark v-on="on">Add Hero</v-btn>
			</template>
			<v-card>
				<v-card-title class="headline grey lighten-2" primary-title
					>Add a New Project</v-card-title
				>
				<HeroForm v-on:add-hero="addHero" />
			</v-card>
		</v-dialog>
	</div>
</template>

<script>
import HeroForm from './HeroForm';
export default {
	components: {
		HeroForm,
	},

	data() {
		return { dialog: false };
	},

	methods: {
		addHero () {
			const hero = this.add-hero
			this.$emit('new-hero', hero)
		}
	},
};
</script>

<style lang="scss" scoped></style>
