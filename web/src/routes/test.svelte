<script lang="ts">
	import { operationStore, query } from '@urql/svelte';
	import { GetLaunchesDocument } from '../graphql-operations';

	const launches = query(operationStore(GetLaunchesDocument));
</script>

<svelte:head>
	<title>GraphQL Test</title>
</svelte:head>

{#if $launches.fetching}
	<p>Loading...</p>
{:else if $launches.error}
	<p>Oh no... {$launches.error.message}</p>
{:else}
	<ul>
		{#each $launches.data?.launches as todo}
    {#if  todo.details}
    <li>{todo.details}</li>
    {/if}    

		{/each}
	</ul>
{/if}
