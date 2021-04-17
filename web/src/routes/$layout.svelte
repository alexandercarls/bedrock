<script>
	import '../app.css';

	import { initClient } from '@urql/svelte';

	initClient({
		url: 'https://space-x-land-with-sub.herokuapp.com/graphql/'
	});
</script>

<slot />
