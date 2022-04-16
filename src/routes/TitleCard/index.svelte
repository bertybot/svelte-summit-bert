<script context="module">
	/** @type {import('./').Load} */
	export async function load({ params, fetch, url }) {
		const href = url.searchParams.get('href');
		return {
			status: 200,
			props: {
				href
			}
		};
	}
</script>

<script>
	export let href;
	import TitleCard from '$lib/TitleCard/TitleCard.svelte';
</script>

<a {href}>
	<TitleCard />
</a>
