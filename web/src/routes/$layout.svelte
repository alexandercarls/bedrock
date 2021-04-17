<script>
	import '../app.css';

	import { initClient } from '@urql/svelte';
import Nav from '$lib/Nav.svelte';

	initClient({
		url: 'https://space-x-land-with-sub.herokuapp.com/graphql/'
	});
</script>

<Nav />

<main>
<slot />
</main>

<style>
	main {

		margin: 2rem;
		/* text-align: center; */
		/* padding: 0em; */
		/* margin: -1 auto; */
	}
</style>