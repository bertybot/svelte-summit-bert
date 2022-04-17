<script>
	import { fly } from 'svelte/transition';
	import ColorBar from './ColorBar.svelte';
	import Ballons from './Ballons.svelte';
	import GreenScreen from '$lib/GreenScreen.svelte';
	const colors = [
		'bg-red-500',
		'bg-orange-500',
		'bg-yellow-500',
		'bg-green-500',
		'bg-blue-500',
		'bg-purple-500',
		'bg-pink-500'
	];
</script>

<GreenScreen>
	<div
		transition:fly={{ delay: 0, duration: 1200, x: -1200, y: 0, opacity: 0.5 }}
		class="inline-flex w-screen items-center pt-10"
	>
		<div class="grid text-center w-full">
			<p class="relative w-full top-36 font-bold text-9xl text-white">CONGRATULATIONS!!!!</p>
			{#each colors as color}
				<ColorBar {color} />
			{/each}
		</div>
	</div>
	<Ballons {colors} />
</GreenScreen>

<style>
	p {
		-webkit-text-stroke: 5px black;
	}
</style>
