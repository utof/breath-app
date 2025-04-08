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

<div class="flex h-screen items-center justify-center bg-amber-100">
	<div class="max-w-md min-w-[200px] bg-red-300 text-center">
		<h1 class="mb-4 text-4xl">Welcome</h1>
		{#each texts as text}
			<Button name={text.name} />
		{/each}
		<Breath onClick={() => showBreath()} />
	</div>
</div>
