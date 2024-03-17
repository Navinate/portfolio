<script>
// @ts-nocheck

	import { Float, Text } from "@threlte/extras";
    import { T } from '@threlte/core'
    import {words, links, colors} from '../data.js'
    import Orb from "./Orb.svelte";
    const positions = [[0,0.8,0],[1.5,-0.8,0],[3,0.8,0],[4.5,-0.8,0],[6,0.8,0],[7.5,-0.8,0]];

</script>

<T.OrthographicCamera makeDefault position={[0, 0, 1]} zoom={50} />

  <T.DirectionalLight
    intensity={3}
    position.x={-5}
    position.y={-10}
  />
<!-- <Float
  floatIntensity={5}
  floatingRange={[-5, 5]}>
  <T.DirectionalLight
    intensity={5}
    position.x={5}
    position.y={10}
    position.z={5}
    color="#FF0000"
  />
</Float> -->
<T.AmbientLight intensity={1} />
<Float
    floatIntensity={1}
    floatingRange={[-0.2, 0.2]}
>
    <Text
        position={[-5, 0, 0]}
        renderOrder={-5}
        text="Trey's Noise"
        color="#d42035"
        textAlign="center"
        font="/fonts/fredokaone.ttf"

        glyphGeometryDetail={10}
        gpuAccelerateSDF={true}
        letterSpacing={0.02}
        lineHeight={1.2}
        outlineColor="#8231C4"
        outlineOffsetX={0.02}
        outlineOffsetY={0.02}
        outlineOpacity={0.5}
        outlineWidth={0.01}
        fontSize={1}
        anchorX="50%"
        anchorY="50%"

        on:click={() => {
          alert("You clicked the title!");
          window.location.href = "/";
        }}
    />
</Float>

{#each positions as position, i}
  <Orb position={position} text={words[i]} targetURL={links[i].replace("/content", "")} color={colors[i]} floatAmp={0.5} floatRange={0.2} opacity={0.9}/>
{/each}

