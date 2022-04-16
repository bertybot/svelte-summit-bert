<script>
    export let number = 2;
    export let title = 'OUR CODEBASE TODAY'
	import TitleCard from '$lib/TitleCard/TitleCard.svelte';
</script>

<a href="/Radial/green">
	<TitleCard {number} {title} />
</a>
