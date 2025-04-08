<script lang="ts">
	import Button from '../lib/Button.svelte';
	import Breath from '../lib/Breath.svelte';
	const texts: any[] = [
		{ name: 'breaths', amount: '30' },
		{ name: 'retention', amount: '1.50' }
	];

	function showBreath(): void {
		console.log('a');
	}
</script>

<div class="align-center flex-row justify-center bg-amber-400">
	<h1 class="text-4xl">Welcome</h1>
	{#each texts as text}
		<Button name={text.name} />
	{/each}
	<Breath onClick={() => showBreath()} />
</div>
