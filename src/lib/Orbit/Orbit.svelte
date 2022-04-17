<script>
	//only works in firefox
	//Svelte conversion of this https://github.com/kevin-powell/seamless-can-i-clone-it
	
	import Circle from './Circle.svelte';
	import GreenScreen from '$lib/GreenScreen.svelte';
	import { tweened } from 'svelte/motion';
	import logos from './logos';
import { onDestroy, onMount } from 'svelte';
	const images = logos;
	let speed = 5;
	let interval;

	onMount(() => {
		setInterval(() => speed = speed === 1 ? 1 : speed -= 1, 1000);
	})
	onDestroy(() => {
		clearInterval(interval)
	})
</script>

<GreenScreen>
	<div style:--speed={`${speed}s`} class="orbit mx-auto my-auto">
		<ul>
			{#each images as image}
				<Circle {...image} />
			{/each}
		</ul>
	</div>
</GreenScreen>

<style lang="scss">
	.orbit {
		--size: 12rem;
		--speed: 5s;
		ul {
			display: grid;
			place-items: center;
			width: var(--size);
			height: var(--size);
			position: relative;
			list-style: none;
			transform-origin: center;
			animation: orbit var(--speed) linear infinite;
		}
	}
	@keyframes orbit {
		100% {
			rotate: 1turn;
		}
	}
</style>
