<script>
	export let src = '';
	export let alt = '';
</script>

<li>
	<div>
		<img {src} {alt} />
	</div>
</li>

<style lang="scss">
	li {
		position: absolute;
		width: 8rem;
		aspect-ratio: 1 / 1;
		line-height: 1;
		display: grid;
		place-items: center;

		& > * {
			width: 100%;
			height: 100%;
			display: grid;
			place-items: center;

			position: absolute;
			animation: orbit var(--speed) linear reverse infinite;
		}
	}

	li:nth-child(1) {
		transform: translate(15rem, 0rem);
	}

	li:nth-child(2) {
		transform: translate(10rem, 10rem);
	}

	li:nth-child(3) {
		transform: translate(0, 15rem);
	}
	li:nth-child(4) {
		transform: translate(-10rem, 10rem);
	}

	li:nth-child(5) {
		transform: translate(-15rem, 0rem);
	}

	li:nth-child(6) {
		transform: translate(-10rem, -10rem);
	}

	li:nth-child(7) {
		transform: translate(0, -15rem);
	}
	li:nth-child(8) {
		transform: translate(10rem, -10rem);
	}
	@keyframes orbit {
		100% {
			rotate: 1turn;
		}
	}

	@keyframes hold-position {
		100% {
			rotate: -1turn;
		}
	}

	@keyframes throb {
		100% {
			scale: 1.05;
		}
	}
</style>
