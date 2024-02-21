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

<style>
    main {
        max-width: 1080px;
        margin: 0 auto;
        padding: 2rem;
        height: 100vh;
        background-color: #0c111d;
        color: white;
    }
    header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 2rem;
    }

</style>
