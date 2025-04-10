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
		current_state = statevals.CHOOSING;
	}
</script>

<div class="flex h-screen items-center justify-center bg-amber-100">
	<div class="max-w-md min-w-[200px] bg-red-300 text-center">
		<h1 class="mb-10 text-4xl">Welcome</h1>
		{#if current_state === statevals.CHOOSING}
			<Choosing params={breath_params} />
		{:else}
			<h1>hi</h1>
		{/if}
		<Breath params={breath_params} onClick={() => showBreath()} />
	</div>
</div>
