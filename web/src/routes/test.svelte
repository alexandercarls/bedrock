<script lang="ts">
	import { operationStore, query } from '@urql/svelte';
	import { GetLaunchesDocument } from '../graphql-operations';

	const launches = query(operationStore(GetLaunchesDocument));
</script>

{#if $launches.fetching}
	<p>Loading...</p>
{:else if $launches.error}
	<p>Oh no... {$launches.error.message}</p>
{:else}
	<ul>
		{#each $launches.data?.launches as todo}
			<li>{todo.details}</li>
		{/each}
	</ul>
{/if}
