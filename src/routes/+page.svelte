<script>
	import App from '$lib/components/App.svelte';
</script>

<header>Trey's Portfolio</header>
<div>
	<App />
</div>
<footer>© 2021 Trey's Noise</footer>

<style>
	:global(body) {
		margin: 0;
	}

	div {
		width: 100vw;
		height: 100vh;
	}

	header {
		font-family: 'Fredokaone', monospace;
		padding: 1.5rem;
		height: 10rem;
		font-size: 3rem;
		text-align: center;
		position: fixed;
		top: 0;
		left: 0;
		width: 100vw;
		background: linear-gradient(0deg, rgba(121, 116, 209, 0) 0%, rgba(212, 32, 53, 1) 100%);
		color: white;
	}
</style>
