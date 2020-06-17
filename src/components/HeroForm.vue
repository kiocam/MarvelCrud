<template>
	<div>
		<form @submit="addHero">
			<input
				type="text"
				v-model="heroName"
				name="heroName"
				placeholder="Hero Name"
			/>
			<input
				type="text"
				v-model="image"
				name="image"
				placeholder="Image Link"
			/>
			<div class="stats">
				<label for="Int">Int: </label>
				<input v-model="int" type="text" name="Int" />

				<label for="str">Str: </label>
				<input v-model="str" type="text" name="str" />

				<label for="speed">Speed: </label>
				<input v-model="speed" type="text" name="speed" />

				<label for="dra">Durability: </label>
				<input v-model="dura" type="text" name="dra" />

				<label for="pwr">Power: </label>
				<input v-model="power" type="text" name="pwr" />

				<label for="cbt">Combat: </label>
				<input v-model="combat" type="text" name="cbt" />
			</div>
			<textarea
				v-model="bio"
				type="text"
				name="heroBio"
				placeholder="Hero Bio"
			/>

			<button class="btn" type="submit">Add Hero</button>
		</form>
	</div>
</template>

<script>
export default {
	name: 'HeroForm',
	data() {
		return {
			heroName: '',
			int: '',
			str: '',
			speed: '',
			dura: '',
			power: '',
			combat: '',
			bio: '',
			image: '',
		};
	},

	methods: {
		addHero(e) {
			e.preventDefault();
			const newHero = {
				name: this.heroName,
				powerstats: {
					intelligence: this.int,
					strength: this.str,
					speed: this.speed,
					durability: this.dura,
					power: this.power,
					combat: this.combat,
				},
				image: this.image,
				bio: this.bio,
			};
			this.$emit('add-hero', newHero);
		},
	},
};
</script>

<style lang="scss" scoped>
form {
	display: flex;
	justify-content: space-between;
	flex-wrap: wrap;
	margin: 20px;

	input {
		border: none;
		border-bottom: 1px solid #585858;
		//padding-bottom: 15px;
	}

	.stats {
		input {
			width: 50px;
			margin: 20px 20px;
		}
	}
}

textarea:focus,
input:focus {
	border: none;
	border-bottom: 2px solid #d63031;
	outline: none;
}

textarea {
	width: 400px;
	border-bottom: 1px solid #585858;
	margin-bottom: 60px;
}

.btn {
	width: 150px;
	padding: 10px 5px;
	background: transparent;
	border: 2px solid #d63031;
	border-radius: 2px;
	font-size: 1em;
	font-weight: bold;
	margin-bottom: 30px;
}
</style>
