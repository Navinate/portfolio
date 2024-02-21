<script>
  import { T } from '@threlte/core'
  import { OrbitControls } from '@threlte/extras'
  import { Stars } from '@threlte/extras'
  import {words, links, colors} from '../data.js'
  import Orb from './Orb.svelte'

  const positions = [[-3, 0, -3], [-3, 1, 3],   [3, -1, -3], [2, 0, 3],     [4, 2, -1],        [1, 3, 4]];

  let zoom = window.screen.width > 1280 ? 0.5 : 0.2;

  window.addEventListener('resize', () => {
    zoom = map(window.screen.width, 0, 1280, 0.1, 0.5);
  });

  /**
	 * @param {number} value
	 * @param {number} low1
	 * @param {number} high1
	 * @param {number} low2
	 * @param {number} high2
	 */
  function map(value, low1, high1, low2, high2) {
    return low2 + (value - low1) * (high2 - low2) / (high1 - low1)
  }
</script>

<Stars />

<T.PerspectiveCamera
  makeDefault
  position={[-10, 10, 10]}
  fov={15}
  zoom={zoom}
>
  <OrbitControls
    autoRotate
    enableZoom={false}
    enableDamping
    autoRotateSpeed={0.5}
  />
</T.PerspectiveCamera>

<T.DirectionalLight
  intensity={5}
  position.x={-5}
  position.y={-10}
/>
<T.AmbientLight intensity={1} />

{#each positions as position, i}
  <Orb position={position} text={words[i]} targetURL={links[i]} color={colors[i]}/>
{/each}

