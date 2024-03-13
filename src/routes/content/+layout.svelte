<script>
	import { Canvas } from "@threlte/core";
    import HeaderScene from "$lib/components/HeaderScene.svelte";
</script>
<svelte:head>
    <title>About Me</title>
</svelte:head>

<main>
    <header>
        <Canvas
            size={{width: 900, height:300}}
        >
            <HeaderScene />
        </Canvas>
    </header>
    <slot></slot>
</main>
<footer>
    <p>Made with 🍭 by Trey in 2024</p>
</footer>

<style>
    main {
        max-width: 1080px;
        margin: 0 auto;
        padding: 2rem;
        background-color: #0c111d;
        color: white;
    }
    header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 2rem;
    }

    footer {
        margin-top: 4rem;
        padding: 2rem;
        background-color: var(--accent-six);
        background-image: linear-gradient(45deg, var(--accent-one), var(--accent-six));
        color: white;
        text-align: center;
        font-size: 1.5rem;
    }

</style>
