<script>
    export let number = 3;
    export let title = 'Training'
	import TitleCard from '$lib/TitleCard/TitleCard.svelte';
</script>

<a href="/Radial/green">
	<TitleCard {number} {title} />
</a>