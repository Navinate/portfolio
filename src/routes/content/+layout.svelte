<script>
	import { Canvas } from "@threlte/core";
    import HeaderScene from "$lib/components/HeaderScene.svelte";
	import MobileHeaderScene from "$lib/components/MobileHeaderScene.svelte";
	import { onMount } from "svelte";

    let windowWidth = 0;
    onMount(()=> {
        windowWidth = window.screen.width;
    
    })
</script>

<main>

    <header>
        {#if windowWidth > 720}
            <Canvas
                size={{width: 900, height:200}}
            >
                <HeaderScene />
            </Canvas>
        {:else}
            <Canvas
                size={{width: windowWidth, height:100}}
            >
                <MobileHeaderScene />
            </Canvas>
        {/if}
        
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
        background-color: var(--red);
        background-image: linear-gradient(45deg, var(--blue), var(--red));
        color: white;
        text-align: center;
        font-size: 1.5rem;
    }

</style>
