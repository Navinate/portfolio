<script>
  import { Canvas } from '@threlte/core'
	import DesktopScene from './DesktopScene.svelte';
	import MobileScene from './MobileScene.svelte';
</script>

<Canvas>
  {#if window.screen.width > 720}
    <DesktopScene />
  {:else}
    <MobileScene />
  {/if}
</Canvas>
