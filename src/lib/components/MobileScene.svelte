<script>
// @ts-nocheck

  import { T } from '@threlte/core'
  import { Stars } from '@threlte/extras'
  import {words, links, colors} from '../data.js'

  import Orb from './Orb.svelte'

  const positions = [[0,2.5,1],[0,2.5,-1],[0,0,1],[0,0,-1],[0,-2.5,1],[0,-2.5,-1]];
</script>

<T.PerspectiveCamera
  makeDefault
  position={[10, 0, 0]}
  on:create={({ ref }) => {
    ref.lookAt(0, 0, 0)
  }}
/>
<T.DirectionalLight
  intensity={5}
  position.x={-5}
  position.y={-10}
/>
<T.AmbientLight intensity={1} />

{#each positions as position, i}
  <Orb position={position} text={words[i]} targetURL={links[i]} color={colors[i]} floatAmp={0.5}/>
{/each}

<Stars />
