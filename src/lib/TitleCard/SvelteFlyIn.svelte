<script>
	import Logo from './svelte.webp';
	import { fly } from 'svelte/transition';
</script>

<div
	in:fly={{ delay: 0, duration: 2200, x: -1200, y: 0, opacity: 0.5 }}
	class="inline-flex w-11/12 md:w-3/4 items-center pt-10"
>
	<div class="flex bg-[#FF3E00] h-24 w-full items-center">
		<div class="w-full bg-white h-10" />
	</div>
	<img class="h-72 z-10 relative right-3" alt="logo" src={Logo} />
</div>
