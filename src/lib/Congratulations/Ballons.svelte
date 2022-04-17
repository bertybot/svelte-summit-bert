<script>
	const dots = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
	const maxDelay = 1000;
	const defaultDelay = 1000;

	let dotArray = [];

	export let colors = [];

	function getRandomInt(max) {
		return Math.floor(Math.random() * max);
	}
	function getRandomDots() {
		return dots.map((item) => {
			return {
				id: item,
				left: `${getRandomInt(98)}%`,
				delay: defaultDelay + getRandomInt(maxDelay),
				color: colors[getRandomInt(colors.length)]
			};
		});
	}

	$: dotArray = getRandomDots();
</script>

{#each dotArray as { id, left, delay, color } (id)}
	<div
		style:left
		style:animation-delay={`${delay}ms`}
		class="absolute rounded-full h-36 w-32 {color}"
	/>
{/each}

<style>
	@keyframes flyUp {
		0% {
			top: 98%;
			opacity: 1;
		}
		60% {
			opacity: 1;
		}
		100% {
			opacity: 0;
			top: 1%;
		}
	}
	div {
		opacity: 0;
		animation: flyUp 2000ms 1;
	}
</style>
