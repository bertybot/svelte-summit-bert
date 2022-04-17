<script>
	const dots = [1, 2, 3, 4, 5, 6, 7, 8];
	const maxDelay = 1000;
	const defaultDelay = 1000;

	let dotArray = [];

	function getRandomInt(max) {
		return Math.floor(Math.random() * max);
	}
	function getRandomDots() {
		return dots.map((item) => {
			return {
				id: item,
				top: `${getRandomInt(99)}%`,
				left: `${getRandomInt(99)}%`,
				delay: defaultDelay + getRandomInt(maxDelay)
			};
		});
	}

	$: dotArray = getRandomDots();
</script>

{#each dotArray as { id, top, left, delay } (id)}
	<div
		style:top
		style:left
		style:animation-delay={`${delay}ms`}
		class="absolute rounded-full w-5 h-5 bg-white"
	/>
{/each}

<style>
	@keyframes fadeIn {
		/* flame pulses */
		0% {
			opacity: 0;
		}
		50% {
			opacity: 1;
		}
		100% {
			opacity: 0;
		}
	}
	div {
		opacity: 0;
		animation: fadeIn 2000ms 1 ease;
	}
</style>
