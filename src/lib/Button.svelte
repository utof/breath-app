<script lang="ts">
	export let name: string;
	export let value: number = 0;
	function handleInput(event: Event) {
		const input = event.target as HTMLInputElement;
		value = parseInt(input.value) || 0; // Fallback to 0 if input is invalid
	}
</script>

<div class="flex items-center gap-4">
	{name}
	<input
		type="number"
		bind:value
		on:input={handleInput}
		class="w-16 rounded border px-2 text-center"
	/>
</div>
