<script lang="ts">
	import Button from '../lib/Button.svelte';
	const texts: any[] = [
		{ name: 'breaths', amount: '30' },
		{ name: 'retention', amount: '1.50' }
	];
</script>

<h1 class="text-4xl">Welcome to SvelteKit</h1>
{#each texts as text}
	<Button name={text.name} />
{/each}
<!-- <Button {text} /> -->
<p>Visit <a href="https://svelte.dev/docs/kit">svelte.dev/docs/kit</a> to read the documentation</p>
