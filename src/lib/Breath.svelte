<script lang="ts">
	let { params } = $props();

	let breath_substate = {
		IN: 'in',
		OUT: 'out',
		OUT_HOLD: 'out_hold',
		IN_HOLD: 'in_hold',
		PAUSE: 'pause'
	};
	$effect(() => breathIn());
	let round_state = $state(1);

	let current_substate = $state(breath_substate.IN);

	let breathOut = () => {
		current_substate = breath_substate.OUT;
		setTimeout(breathIn, 2200);
	};

	let breathIn = () => {
		current_substate = breath_substate.IN;
		setTimeout(breathOut, 2000);
	};
</script>

<h1 class="text-4xl">
	<div>
		{params.breaths}
		{params.sheesh}
	</div>
	current substate {current_substate}
</h1>

<style>
</style>
