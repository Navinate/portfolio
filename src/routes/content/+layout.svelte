<script>
	import { Canvas } from '@threlte/core';
	import HeaderScene from '$lib/components/HeaderScene.svelte';
	import MobileHeaderScene from '$lib/components/MobileHeaderScene.svelte';
	import { onMount } from 'svelte';

	$: innerWidth = 0;
</script>

<svelte:window bind:innerWidth />
<header>
	{#if innerWidth > 720}
		<Canvas size={{ width: innerWidth, height: 200 }}>
			<HeaderScene />
		</Canvas>
	{:else}
		<Canvas size={{ width: innerWidth, height: 100 }}>
			<MobileHeaderScene />
		</Canvas>
	{/if}
</header>
<main>
	<slot />
</main>
<footer>
	<p>Made with 🍭 by Trey in 2024</p>
</footer>

<style>
	main {
		max-width: 720px;
		margin: 0 auto;
		color: white;
		padding-bottom: 1rem;
	}
	header {
		display: flex;
		justify-content: space-between;
		align-items: center;
		margin-bottom: 2rem;
	}
	footer {
		padding: 2rem;
		background-color: var(--red);
		background-image: linear-gradient(45deg, var(--blue), var(--red));
		color: white;
		text-align: center;
		font-size: 1.5rem;
	}

	@media (max-width: 720px) {
		main {
			padding: 0 1rem;
		}
	}
</style>
