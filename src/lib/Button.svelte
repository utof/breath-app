<script lang="ts">
	let { name, clickhandler } = $props();
</script>

<h1>HELLO {name}</h1>
<button
	onclick={() => {
		clickhandler;
	}}
>
	clickme
</button>
