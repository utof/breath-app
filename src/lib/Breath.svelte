<script lang="ts">
	let params = $props();

	let breath_substate = {
		IN: 'in',
		OUT: 'out',
		OUT_HOLD: 'out_hold',
		IN_HOLD: 'in_hold',
		PAUSE: 'pause'
	};

	let round_state = $state(1);

	let current_substate = $state(breath_substate.IN);

	function breathIn() {}
</script>

<h1 class="text-4xl">
	<div>
		{params}
	</div>
	BREATHINGGGGG
</h1>

<style>
</style>
