<script>
    export let number = 4;
    export let title = 'DEPLOYING TO PRODUCTION!!!'
	import TitleCard from '$lib/TitleCard/TitleCard.svelte';
</script>

<TitleCard {number} {title} />