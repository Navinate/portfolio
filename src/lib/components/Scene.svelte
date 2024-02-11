<script>
  import { T } from '@threlte/core'
  import { ContactShadows, Grid, OrbitControls } from '@threlte/extras'
  import { Stars } from '@threlte/extras'

  import Orb from './Orb.svelte'

  const positions = [[-2, 0, -2], [-2, 0, 2], [2, 0, -2], [2, 0, 2]]
  const words = ['Trey', 'Orb', 'Portfolio', 'StairWELL']
</script>

<Stars />

<T.PerspectiveCamera
  makeDefault
  position={[-15, 15, 15]}
  fov={15}
>
  <OrbitControls
    autoRotate
    enableDamping
    autoRotateSpeed={0.2}
  />
</T.PerspectiveCamera>

<T.DirectionalLight
  intensity={5}
  position.x={5}
  position.y={10}
/>
<T.AmbientLight intensity={1} />

{#each positions as position, i}
  <Orb position={position} text={words[i]}/>
{/each}

