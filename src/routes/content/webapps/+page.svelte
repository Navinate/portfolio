<svelte:head>
	<title>My Web Apps</title>
</svelte:head>
<h1>My Web Creations</h1>
<section>
	<h3>Albers Challenge - 2023</h3>
	<ul class="sideways">
		<a href="https://svelte.dev/"><li>SvelteKit</li></a>
		<a href="https://www.vercel.com"><li>Vercel Hosted</li></a>
	</ul>
	<a href="https://albers.navinate.com">
		<img src="/images/albers.png" alt="Screenshot of my color guessing game: Albers' Challenge" />
	</a>
	<p>
		A fun little game I made while @ <a href="https://www.purduehackers.com/">Purdue Hackers</a>
		hack night. The goal is to guess the presented color even though it is being contrasted by random
		colors. The design is inspired by fun and
		<a href="https://www.albersfoundation.org/">Josef Albers'</a>
		work. <a href="https://albers.navinate.com">Link</a> and
		<a href="https://github.com/purduehackers/albers-challenge">Source</a>
	</p>
</section>
<section>
	<h3>Stratagem ➡️ Emoji - 2024</h3>
	<ul class="sideways">
		<a href="https://svelte.dev/"><li>SvelteKit</li></a>
		<a href="https://www.vercel.com"><li>Vercel Hosted</li></a>
	</ul>
	<a href="https://stratagem-emoji.vercel.app/">
		<img src="/images/stratagem.png" alt="Screenshot of my Stratagem code tool" />
	</a>
	<p>
		Small web app I made to quickly convert WASD / Arrow key inputs into emojis. Inspired by the
		amazing game Helldivers 2. <a href="https://stratagem-emoji.vercel.app/">Link</a> and
		<a href="https://github.com/Navinate/stratagem-emoji">Source</a>
	</p>
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

	.sideways a li,
	p a {
		text-decoration: none;
		background-color: var(--red);
		color: white;
		cursor: pointer;
		text-decoration: underline;
		transition-duration: 0.1s;
	}
	.sideways a li:hover,
	p a:hover {
		transform: scale(1.1);
	}
	p a {
		border-radius: 0.5rem;
		padding: 0.5rem 0.5rem;
		cursor: pointer;
		background-color: var(--background-color);
	}
	img {
		border-radius: 1rem;
		box-shadow: 0px 0px 5px rgba(0, 0, 0, 0.5);
		width: 80vw;
		max-width: 560px;
	}

	@media (max-width: 720px) {
		h1 {
			font-size: 2rem;
		}
		h3 {
			font-size: 1.5rem;
		}
		h1,
		h3 {
			line-height: 1rem;
		}
	}
</style>
