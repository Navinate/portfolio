<script>
// @ts-nocheck

	import { Float, Text } from "@threlte/extras";
    import { T } from '@threlte/core'
    import {words, links, colors} from '../data.js'
    import Orb from "./Orb.svelte";
    const positions = [[0,1,0],[1.5,-1,0],[3,1,0],[4.5,-1,0],[6,1,0],[7.5,-1,0]];

</script>

<T.OrthographicCamera makeDefault position={[0, 0, 10]} zoom={50} />
<T.DirectionalLight
  intensity={5}
  position.x={-5}
  position.y={-10}
/>
<T.AmbientLight intensity={1} />
<Float
    floatIntensity={1}
    floatingRange={[-0.5, 0.5]}
>
    <Text
        position={[-5, 0, 0]}
        renderOrder={-5}
        text="Trey's Noise"
        color="#009DDC"
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
    />
</Float>

{#each positions as position, i}
  <Orb position={position} text={words[i]} targetURL={links[i].replace("/content", "")} color={colors[i]} floatAmp={0.5} opacity={0.9}/>
{/each}

