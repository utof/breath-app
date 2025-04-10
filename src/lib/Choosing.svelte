<script lang="ts">
	export let params: Record<string, number>;
	function handleInput(event: Event, key: string) {
		const input = event.target as HTMLInputElement;
		params[key] = parseInt(input.value) || 0; // Fallback to 0 if input is invalid
	}
</script>

<div class="flex flex-col gap-4 text-2xl">
	<div class="bg-gray-100 p-6 font-light">
		{#each Object.entries(params) as [key, value]}
			<div class="mb-6 flex justify-between">
				<span class="mx-8">{key}</span>
				<input
					type="number"
					{value}
					on:input={(e) => handleInput(e, key)}
					class="w-16 rounded border border-hidden px-2 text-center"
				/>
			</div>
		{/each}
	</div>
</div>
