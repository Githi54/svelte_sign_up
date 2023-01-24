<script lang="ts">
	export let value: any;
    export let label: string;
    export let type = 'text';
	
	function typeAction(node: HTMLInputElement){
		node.type = type;
	}
</script>

<p class="form-control">
	{#if label}
		<label class="label" for>{label}:</label>
	{/if}
	<input use:typeAction class="input" bind:value={value} required/>
</p>

<style>
	.form-control{
		margin: .5rem 0;
		text-align: left;
	}
	.input{
		width: 100%;
		display: block;
		padding: 0.5rem 0;
		margin-top: 0.5rem;
		border-width: 1px;
		border-radius: 0.25rem;
	}

</style>