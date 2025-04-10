<script lang="ts">
	import Choosing from '../lib/Choosing.svelte';
	import Breath from '../lib/Breath.svelte';
	const statevals = {
		CHOOSING: 'choosing',
		BREATHING: 'breathing',
		FINISHED: 'finished'
	};
	let current_state = $state(statevals.CHOOSING);

	const breath_params: Record<string, number> = $state({
		breaths: 30,
		sheesh: 1.3
	});

	function showBreath(): void {
		console.log('a');
		current_state = statevals.BREATHING;
	}
</script>

<div class="flex h-screen items-center justify-center rounded-full bg-gray-50">
	<div class="w-3xl max-w-md min-w-[200px] overflow-hidden rounded-4xl bg-cyan-100 p-6 text-center">
		<h1 class="mb-10 text-4xl">WIM 4 DA WIN</h1>
		{#if current_state === statevals.CHOOSING}
			<Choosing params={breath_params} />
		{:else}
			<Breath params={breath_params} />
		{/if}
		<button class="rounded-3xl bg-amber-400 px-[0.25em] text-3xl" onclick={() => showBreath()}>
			Begin breathwork
		</button>
	</div>
</div>
