<script>
	import Header from "$lib/Header/index.svelte";
	import "../app.css";
	const year = new Date().getFullYear();
</script>

<Header />

<main>
	<slot />
</main>

<footer>
	<p>
		plannings équipe Arcs de Seine &copy; {year}
	</p>
	<p>
		<a href="https://github.com/Fabezio/svelte-plannings">code source</a>
	</p>
</footer>

<style>
	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		padding: 1rem;
		width: 100%;
		max-width: 1200px;
		margin: 0 auto;
		box-sizing: border-box;
	}

	footer {
		display: flex;
		flex-direction: row;
		justify-content: space-evenly;
		align-items: center;
		padding: 40px;
	}

	footer a {
		font-weight: bold;
	}

	/* @media (min-width: 480px) {
		footer {
			padding: 40px 0;
		}
	} */
</style>
