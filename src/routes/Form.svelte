<script lang="ts">
	import InputField from './InputField.svelte';
	export let active_step: any;
	export let formData = {
		carBrand: '',
        carModel: '',
		zipCode: '',
		firstName: '',
		lastName: '',
        firstRagistration: '',
	};

	const handleSubmit = () => {
		console.log('Your form data => ', formData);
	};
</script>

<form class="form-container" on:submit|preventDefault={handleSubmit}>
	{#if active_step == 'CarInfo'}
		<InputField label={'Car brand'} bind:value={formData.carBrand} />
		<InputField label={'Zip code'} bind:value={formData.zipCode} />
	{:else if active_step == 'Contacts'}
		<InputField label={'Firstname'} bind:value={formData.firstName} />
		<InputField label={'Lastname'} bind:value={formData.lastName} />
		<InputField label={'Car model'} bind:value={formData.carModel} />
		<InputField type='checkbox' label={'First registartion'} bind:value={formData.firstRagistration} />
        <button class="btn submit">Finish </button>
	{/if}
</form>

<style>
	.form-container {
		background-color: #fff;
		border-radius: 10px;
		box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1), 0 6px 6px rgba(0, 0, 0, 0.1);
		padding: 50px 20px;
		text-align: center;
		max-width: 100%;
		width: 350px;
	}
	.btn {
		color: white;
		padding: 0.5rem 0;
		margin-top: 0.5rem;
		display: inline-block;
		width: 100%;
		border-radius: 0.25rem;
		cursor: pointer;
	}
	.submit {
		background: linear-gradient(to bottom, #44c767 5%, #50b01c 100%);
		background-color: #44c767;
	}
	.submit:hover {
		background: linear-gradient(to bottom, #50b01c 5%, #44c767 100%);
		background-color: #50b01c;
	}
</style>
