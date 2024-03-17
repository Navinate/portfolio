<svelte:head>
    <title>My School Projects</title>
</svelte:head>
<h1>Various School Projects</h1>
<section>
    <h3>Plantview - 2022</h3>
    <ul class="sideways">
        <li>Virtual Enviroment</li>
        <a href="https://www.blender.org/"><li>Blender</li></a>
        <a href="https://godotengine.org/"><li>Godot</li></a>
    </ul>
    <iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/sMj2bU_p31s?si=TXOGA0896CM1bOlJ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
    <p>This is a project I created for my "Gardens and Machines" design class during my Masters program.
          I wanted to recreate the effect of a plant growing in a timelapse in an interactive way.
          In Plantview you can speed up time by pressing spacebar and watch a sprout grow out of the ground after a fresh rain fall.
          View more details in my <a href="https://docs.google.com/presentation/d/1y1T_BY4hL2N88JBJDqjzzyi5_EPG_H3eO78kitpLoJA/edit?usp=sharing">proposal presentation</a></p>
</section>
<section>
    <h3>Unseen Garden - 2022</h3>
    <ul class="sideways">
        <li>Augmented Reality</li>
        <a href="https://www.blender.org/"><li>Blender</li></a>
        <a href="https://aframe.io/"><li>AFrame</li></a>
        <a href="https://www.8thwall.com/"><li>8th Wall</li></a>
    </ul>
    <iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/HiFt9KVknHs?si=DjaP5ZPF_dQgUiLy" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
    <p>This is another project for my "Gardens and Machines" class.  I created a potenial garden that exists everywhere  through AR devices.  The type of flower bloomed at a location is based on Perlin noise.  So mathmatical randomness decides what the garden looks like.  I modeled everything in blender and created the interactivity with Aframe.  8thWall was the class-assigned AR platform</p>
</section>
<section>
    <h3>Still Life - 2021</h3>
    <ul class="sideways">
        <li>Data Visualization</li>
        <a href="https://processing.org/"><li>Processing</li></a>
    </ul>
    <iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/Hi73Z_fqsfI?si=XigGbOvC_IFe4EQE" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
    <p>Still Life is an experimental data visualization of movement.  It is a group project I created for my data visualization class during my Masters program.  My group recorded a timelapse of students walking on campus between classes.  Then we used Processing to analyze the frames of the video and highlight the differences between frames.</p>
</section>
<style>
    * {
        line-height: 3rem;
        font-family: 'Amiamie', sans-serif;
    }
    h1 {
        font-size: 3rem;
        font-family: 'Fredokaone', monospace;
        line-height: 5rem;
        color: var(--teal);
    }
    h3 {
        font-size: 2rem;
        color: var(--teal);
        margin-top: 2rem;
    }

    section > *:not(:first-child) {
        margin-left: 3rem;
    }
    section p {
        text-align: justify;
    }

    ul {
        margin-left: 2rem;
    }
    .sideways {
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        list-style: none outside;
        margin: 1rem;
        gap: 1rem;
    }

    .sideways li {
        border-radius: 0.5rem;
        padding: 0rem 0.5rem;
        cursor: default;
        background-color: var(--blue);
        box-shadow: 0px 0px 5px rgba(0, 0, 0, 0.5);
    }
    p a {
        border-radius: 0.5rem;
        padding: 0.5rem 0.5rem;
        cursor: default;
    }

    .sideways a li, p a {
        text-decoration: none;
        background-color: var(--red);
        color: white;
        cursor: pointer;
        text-decoration: underline;
        transition-duration: 0.1s;
    }
    .sideways a li:hover, p a:hover {
        transform: scale(1.1);
    }

    iframe {
        border-radius: 0.5rem;
        box-shadow: 0px 0px 5px rgba(0, 0, 0, 0.5);
    }

</style>