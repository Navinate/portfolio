<script>
    import { T } from '@threlte/core'
    import { Billboard, Float, Text} from '@threlte/extras'
    import { interactivity } from '@threlte/extras'
	import { spring } from 'svelte/motion'

    export let targetURL = 'https://google.com';
    export let color = '#2A9D8F';
    export let position = [0,0,0];
    export let text = 'Orb';
    export let fontSize = 1;

    const scale = spring(1);
    interactivity();
</script>

<Float
  floatIntensity={1}
  floatingRange={[-0.5, 0.5]}
  >
    <T.Mesh
      renderOrder={1}
      position={position}
      scale={$scale}
      on:pointerenter={() => scale.set(1.1)}
      on:pointerleave={() => scale.set(1)}
      on:click={() => { 
        scale.set(1);
        window.open(targetURL);
      }}
    >
      <T.SphereGeometry
      renderOrder={1}
      />
      <T.MeshPhysicalMaterial
      clearcoat={2}
      emmisiveIntensity={1}
      emmisive={color}
      roughness={0}
      metalness={0.5}
      reflectivity={1}
      iridescence={1}
      iridescenceIOR={2.333}
      sheen={1}
      color={color}
      opacity={0.2}
      transparent
      />
    </T.Mesh>
    <Billboard
    position={position}
    >
        <Text
            {text}
            color="white"
            {fontSize}
            anchorX="50%"
            anchorY="50%"
        />
    </Billboard>
  </Float>