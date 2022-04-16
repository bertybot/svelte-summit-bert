<script>
    import Logo from '$lib/TitleCard/svelte.webp'
	const maxY = 1600;
	const stepY = 100;
	const maxX = 20;
	const stepX = 1;

	/** @returns {import('$lib/types').GridCell[]}*/
	function getRows() {
		let array = [];
		for (let i = 0; i <= maxY; i += stepY) {
			array.push({ text: maxY - i, border: 'border-r-2 border-red-700' });
			for (let j = 0; j <= maxX; j += stepX) {
				if (i === maxY) {
					array.push({ text: j, border: 'border-t-2 border-red-700' });
				} else {
					array.push({ text: '', border: 'border border-green-400' });
				}
			}
		}

		return array;
	}

	$: rows = maxY / stepY + 1;
	$: columns = maxX / stepX + 1;
	$: items = getRows();
</script>

<div class="w-screen h-screen flex justify-center items-center">
	<div
		class="grid relative left-1"
		style:grid-template-columns={`repeat(${columns + 1}, 50px`}
		style:grid-template-rows={`repeat(${rows}, 50px`}
	>
		{#each items as { text, border }}
			<div class="w-full h-full font-bold text-center text-blue-700 {border}">
				{text}
			</div>
		{/each}
        <div style:grid-row-start="{rows}" class="bar absolute rotate-45 left-0 h-full w-96 bg-red-500"><img class=" w-24" alt="test" src={Logo}></div>
	</div>
    
</div>

<style>
    @keyframes scale {
    0% {
        width: 0px;
    }
    100% {
        width: 1000px;
    }
}

    .bar{
        --tw-rotate: 135deg;
        width: 1000px;
        bottom: 400px;
        animation: scale 4000ms 1;
    }
</style>