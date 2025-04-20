<script>
    
    import Countdown from "./Countdown.svelte";

	export let name;
	let p_hello_world = '<p>Hello world' + name +  '</p>';
	let countdown = 6;
</script>

<main>
	<h1>Hello {name}!</h1>
	{@html p_hello_world}
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
	<Countdown countdown = {countdown}/>
</main>


<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>