<script>
  import { T } from '@threlte/core'
  import { ContactShadows, Float, Grid, OrbitControls } from '@threlte/extras'
  import { interactivity } from '@threlte/extras'
  import { spring } from 'svelte/motion'

  interactivity()
  const scale1 = spring(1)
  const scale2 = spring(1)
  const scale3 = spring(1)
  const scale4 = spring(1)
  const scale5 = spring(1)
</script>

<T.PerspectiveCamera
  makeDefault
  position={[-15, 15, 15]}
  fov={15}
>
  <OrbitControls
    autoRotate
    enableZoom={true}
    minZoom={0.5}
    maxZoom={1}
    enableDamping
    autoRotateSpeed={0.5}
  />
</T.PerspectiveCamera>

<T.DirectionalLight
  intensity={0.8}
  position.x={5}
  position.y={10}
/>
<T.AmbientLight intensity={0.5} />

<Grid
  position.y={-0.001}
  cellColor="#ffffff"
  sectionColor="#ffffff"
  sectionThickness={0}
  fadeDistance={25}
  cellSize={2}
/>

<ContactShadows
  scale={10}
  blur={2}
  far={2.5}
  opacity={0.5}
/>

<Float
  floatIntensity={1}
  floatingRange={[-0.5, 0.5]}
  >
    <T.Mesh
      position.x={0}
      position.y={0}
      position.z={0}
      scale={$scale1}
      on:pointerenter={() => scale1.set(1.1)}
      on:pointerleave={() => scale1.set(1)}
      on:click={() => { 
        scale1.set(1);
        window.open('https://google.com');
      }}
    >
      <T.SphereGeometry />
      <T.MeshPhysicalMaterial
      color="#66CED6"
      opacity={0.3}
      transparent
      clearcoat={1}
      />
    </T.Mesh>
    <T.Mesh>
      <T.PlaneGeometry />
    </T.Mesh>
</Float>

