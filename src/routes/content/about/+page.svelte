<svelte:head>
    <title>About Me</title>
</svelte:head>
<h1>About</h1>
<h4>My name is Trey and I am an immersive developer.  I specialize in interactive art, games, and anything involving coding and fun!</h4>
<a href="https://forms.gle/J2jR1y4Gc3QRqi8m8">Resume Request Form</a>
<div>
    <h3>Skills</h3>
    <ul class="sideways">
        <li>HTML</li>
        <li>CSS</li>
        <li>JavaScript</li>
        <li>Typescript</li>
        <li>Svelte</li>
        <li>Three.js</li>
        <li>Processing / P5.js</li>
        <li>Godot</li>
        <li>Blender</li>
        <li>Unity</li>
        <li>Unreal</li>
        <li>Adobe Suite</li>
        <li>C#</li>
        <li>Java</li>
        <li>OpenGL / GLSL</li>
        <li>Git</li>
        <li>Node.js</li>
        <li>SQL</li>
        <li>C++</li>
        <li>PHP</li>     
    </ul>
</div>
<div>
    <h3>Education</h3>
    <ul class="vertical">
        <li><span>Masters</span> in Computational Art</li>
        <li><span>Bachelors</span> in Web Programming and Design</li>
    </ul>
</div>
<div>
    <h3>Jobs</h3>
    <ul class="vertical">
        <li><span>Freelance</span> web and immersive developer: created websites and web apps for small businesses and academic departments</li>
        <li><span>Graduate</span> Research Assistant: creating interfaces with svelte and typescript for LLM backends</li>
        <li><span>Graduate</span> Lab Instructor: taught classroom labs the fundamentals of HTML, CSS, and other web technologies</li>
        <li><span>Student</span> IT Team supervisor: managed the residential netowrking team that handles dorm IT issues on campus</li>
        <li><span>Gaming</span> Cafe employee</li>
    </ul>
</div>

<style>
    * {
        line-height: 3rem;
        font-family: 'Amiamie', sans-serif;
    }
    h1 {
        font-size: 3rem;
        font-family: 'Fredokaone', monospace;
        line-height: 5rem;
        color: var(--accent-one);
    }
    h3 {
        font-size: 2rem;
        color: var(--accent-two);
        margin-top: 2rem;
    }
    h4 {
        font-size: 1.5rem;
        color: var(--accent-three);
    }

    a {
        margin-top: 1.5rem;
        font-size: 1.5rem;
        text-decoration: none;
        background-color: var(--accent-six);
        color: white;
        padding: 0.5rem 1rem;
        border-radius: 0.5rem;
        transition-duration: 0.1s;
    }

    a:hover {
        transform: scale(1.1);
    }

    ul {
        margin-left: 2rem;
    }
    .sideways {
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        list-style: none outside;
        margin-left: 1rem;
        gap: 0.5rem;
    }

    .sideways li {
        border-radius: 0.5rem;
        padding: 0rem 0.5rem;
        cursor: default;
    }
    .sideways li:nth-child(n) {
        background-color: var(--accent-one);
    }
    .sideways li:nth-child(2n) {
        background-color: var(--accent-two);
    }
    .sideways li:nth-child(3n) {
        background-color: var(--accent-three);
    }
    .sideways li:nth-child(4n) {
        background-color: var(--accent-four);
    }
    .sideways li:nth-child(5n) {
        background-color: var(--accent-five);
    }
    .sideways li:nth-child(6n) {
        background-color: var(--accent-six);
    }


    .vertical {
        list-style: outside;
    }

    .vertical li {
        font-size: 1.5rem;
    }

    .vertical li:nth-child(n)::marker {
        color: var(--accent-one);
    }
    .vertical li:nth-child(2n)::marker {
        color: var(--accent-two);
    }
    .vertical li:nth-child(3n)::marker {
        color: var(--accent-three);
    }
    .vertical li:nth-child(4n)::marker {
        color: var(--accent-four);
    }
    .vertical li:nth-child(5n)::marker {
        color: var(--accent-five);
    }
    .vertical li:nth-child(6n)::marker {
        color: var(--accent-six);
    }

    /* .vertical li span {
        color: var(--accent-four);
    } */

</style>