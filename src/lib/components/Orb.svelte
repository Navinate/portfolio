<script>
  import { T } from '@threlte/core'
  import { Billboard, Float, Text, TransformControls} from '@threlte/extras'
  import { interactivity } from '@threlte/extras'
	import { spring } from 'svelte/motion'

  //T.BackSide just isnt working for some reason so I have to import it manually
  import { BackSide } from 'three';



    export let targetURL = 'https://google.com';
    export let radius = 1;
    export let color = '#2A9D8F';
    export let position = [0,0,0];
    export let text = 'Orb';
    export let floatAmp = 1;
    export let opacity = 0.5;
    let fontSize = 5 / text.length * (text.includes("\n") ? 1 : 0.5);

    const scale = spring(radius);
    interactivity();

    /**
	 * @param {string | any[]} hex
	 */
    function invertColor(hex) {
      if (hex.indexOf('#') === 0) {
          hex = hex.slice(1);
      }
      // convert 3-digit hex to 6-digits.
      if (hex.length === 3) {
          hex = hex[0] + hex[0] + hex[1] + hex[1] + hex[2] + hex[2];
      }
      if (hex.length !== 6) {
          throw new Error('Invalid HEX color.');
      }
      // invert color components
      var r = (255 - parseInt(hex.slice(0, 2), 16)).toString(16),
          g = (255 - parseInt(hex.slice(2, 4), 16)).toString(16),
          b = (255 - parseInt(hex.slice(4, 6), 16)).toString(16);
      // pad each with zeros and return
      return '#' + padZero(r) + padZero(g) + padZero(b);
  }

  /**
	 * @param {string} str
	 * @param {number | undefined} [len]
	 */
  function padZero(str, len) {
      len = len || 2;
      var zeros = new Array(len).join('0');
      return (zeros + str).slice(-len);
  }
</script>

<Float
  floatIntensity={floatAmp}
  floatingRange={[-0.5, 0.5]}
  >
    <T.Mesh
      renderOrder={0}
      position={position}
      scale={$scale}
      on:pointerenter={() => scale.set(radius*1.1)}
      on:pointerleave={() => scale.set(radius)}
      on:click={() => { 
        scale.set(radius);
        window.location.href = targetURL;
      }}
    >
      <T.SphereGeometry
      renderOrder={1}
      />
      <T.MeshPhysicalMaterial
      clearcoat={0.5}
      emmisiveIntensity={1}
      emmisive={color}
      roughness={0.2}
      metalness={0.2}
      reflectivity={1}
      iridescence={1}
      iridescenceIOR={2.333}
      sheen={1}
      color={color}
      opacity={opacity}
      transparent={true}
      side={BackSide}
      />
    </T.Mesh>
    <Billboard
    position={position}
    >
        <Text
          renderOrder={-5}
            {text}
            color={invertColor(color)}
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

            {fontSize}
            anchorX="50%"
            anchorY="50%"
        />
    </Billboard>
  </Float>
