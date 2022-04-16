<script>
	import Star from './Star.svelte';
	import Star2 from './Star2.svelte';
	export let color = '#003C7B'
</script>

<div style:background={`radial-gradient(white, ${color})`} class="w-screen radial-gradient h-screen flex items-center justify-center">
	<div class="absolute animate-star-1 top-0 left-0 h-full w-full">
		<Star />
	</div>
	<div class="absolute animate-star-2 top-0 left-0 h-full w-full">
		<Star2 />
	</div>
    <div class="absolute animate-star-1 rotate-180 top-0 left-0 h-full w-full">
		<Star />
	</div>
	<div class="absolute animate-star-2 top-0 left-0 h-full w-full">
		<Star2 />
	</div>
</div>

<style>
	@keyframes flickerAnimation {
		/* flame pulses */
		0% {
			opacity: .15;
            scale: .50;
		}
		50% {
			opacity: 0;
            scale:1;
		}
		100% {
			opacity: .15;
            scale:.50;
		}
	}
	.animate-star-1 {
		opacity: .30;
		animation: flickerAnimation 2s infinite ease;

	}
    .animate-star-2 {
        opacity: .25;
		animation: flickerAnimation 3s infinite ease;
    }
</style>
