<template>
	<div class="card">
		<div class="max-w-sm rounded overflow-hidden shadow-lg">
			<img class="w-56" v-bind:src="hero.image" alt="image" />
			<div class="px-6 py-4">
				<div class="font-bold text-xl mb-2">{{ hero.name }}</div>
				<p class="text-gray-700 text-base mt-6">
					{{ hero.bio }}
				</p>
			</div>
			<div class="px-6 py-4">
				<span
					class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2"
					>Int: {{ hero.powerstats.intelligence }}</span
				>
				<span
					class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2"
					>Str: {{ hero.powerstats.strength }}</span
				>
				<span
					class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700"
					>Spd: {{ hero.powerstats.speed }}</span
				>
				<span
					class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700"
					>Drb: {{ hero.powerstats.durability }}</span
				>
				<span
					class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700"
					>Pwr: {{ hero.powerstats.power }}</span
				>
				<span
					class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700"
					>Cbt: {{ hero.powerstats.combat }}</span
				>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	name: 'Hero',
	props: ['hero'],
};
</script>

<style lang="scss" scoped>
@import 'tailwindcss/base';

@import 'tailwindcss/components';

@import 'tailwindcss/utilities';

.card {
	color: #000;
}
img {
	margin: 0 auto;
}
</style>
