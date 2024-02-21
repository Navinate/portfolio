<svelte:head>
    <script src="https://cdn.jsdelivr.net/npm/zfont/dist/zfont.min.js"></script>
    <script src="https://unpkg.com/zdog@1/dist/zdog.dist.min.js" on:load={registerZdog}></script>
</svelte:head>
<script>
    /* import codeIcon from '/../assets/code.svg';
    import twitterIcon from '/../assets/twitter.svg'; */
    // THANK YOU TO https://jamesdaniel.dev/ for their example on how to use their library Zfont <3
    function registerZdog() {

    // This is a hack to get Zfont to work with Svelte
    // @ts-ignore
    window.Zfont.init(Zdog);
    // @ts-ignore
    let illo = new Zdog.Illustration({
    element: '.zdog-canvas',
    dragRotate: true,
    rotate: {x: -0.12, y: 0.40, z: 0},
    });

    // @ts-ignore
    let font = new Zdog.Font({
    // I also snagged this font from them cause it was so perfect :)
    src: 'fonts/fredokaone.ttf'
    });

    // @ts-ignore
    let text = new Zdog.TextGroup({
        addTo: illo,
        font: font,
        value: "Trey's Noise",
        fontSize: 90,
        translate: {y:-10},
        textAlign: 'center',
        textBaseline: 'middle',
        color: '#468C98',
        fill: true
    });

    let textShadow = text.copyGraph({
        translate: { y:-10, z: -10},
        color: '#C0B9DD'
    });

    // Settings for the wave animation
    let t = 0;
    let tStep = 1;
    let amplitude = 0.2;
    let frequency = 80;

    // Wave function
    // This loops through every shape in a TextGroup and modifies its position according to a sine wave
    // @ts-ignore
    function wave(group) {
    // @ts-ignore
    group.children.forEach(shape => {
        let x = shape.translate.x + t;
        shape.translate.y += amplitude * Math.sin(x / frequency);
    });
    }

    // Animation loop
    function animate() {
        wave(text);
        wave(textShadow);
        t += tStep;
        illo.updateRenderGraph();
        requestAnimationFrame(animate);
    }
    animate();
    }
</script>
<main>
    <canvas class="zdog-canvas" width="580" height="200"></canvas>
    <!-- <div class="info-wrapper">
        <ul class="links">
            <li>
                <a href="https://www.github.com/navinate">
                <img src={codeIcon} alt="Link to my Github" />
                </a>
            </li>
            <li>
                <a href="https://twitter.com/NavinateNoise">
                    <img src={twitterIcon} alt="Link to my Twitter" />
                </a>
            </li>
        </ul>
        <h1>Welcome to my (WIP) portfolio</h1>
    </div> -->
</main>
<style>
    .zdog-canvas {
        display: none;
        cursor: move;
    }
    main {
        display: flex;
        background-color: #ffffff00;
        color: #468C98;
        width: 100%;
        font-weight: bold;
        padding-bottom: 20px;
    }
    .info-wrapper {
        width: 100%;
        padding: 40px 40px 0px 0px;
        text-align: right;
    }

    .links {
        list-style: none;
        display: flex;
        justify-content: flex-end;
        align-items: center;
    }
    .links li {
        font-size: 1.4rem;
        margin: 10px 10px;
    }

    a {
        color: #C0B9DD;
    }

    @media only screen and (min-width: 900px) {
        .zdog-canvas {
            display: block;
        }
        
    }
</style>