<script lang="ts">
	let { params } = $props();

	let breath_in_duration = 2000;
	let breath_out_duration = 2200;

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
		setTimeout(breathIn, breath_out_duration);
	};

	let breathIn = () => {
		current_substate = breath_substate.IN;
		setTimeout(breathOut, breath_in_duration);
	};
</script>

<h1 class="text-4xl">
	<div>
		{params.breaths}
		{params.sheesh}
	</div>
	<div
		class="text-1xl inline-block transition-transform ease-in-out {current_substate ===
		breath_substate.IN
			? 'scale-150'
			: 'scale-100'}"
		style:transition-duration="{current_substate === breath_substate.IN
			? breath_in_duration
			: breath_out_duration}ms"
	>
		O
	</div>
	current substate {current_substate}
</h1>
