<script>
	import SvelteFlyIn from './SvelteFlyIn.svelte';
	import RandomDots from './randomDots.svelte';

	export let number = 1;
	export let title = 'FROM HUMBLE BEGINNINGS';
</script>

<div class="title-card h-screen w-screen">
	<p class="number absolute z-50 left-11 md:left-48 stroke-black font-extrabold">{number}</p>
	<SvelteFlyIn />
	<p class="title w-72 relative left-1/3 line font-bold">{title}</p>
	<RandomDots />
</div>

<style>
	.title {
		font-size: 9rem;
		line-height: 1.2;
	}
	.number {
		font-size: 300px;
		line-height: 1;
	}

	.title-card {
		background: linear-gradient(black, #2409ed);
	}
	p {
		color: rgb(243, 218, 0);
		-webkit-text-stroke: 1px black;
		text-shadow: 3px 3px 0 #000, -1px -1px 0 #000, 15px -1px 0 #000, -1px 1px 0 #000, 1px 1px 0 #000;
	}
</style>
