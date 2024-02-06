<script>
	export let formData;
	let originalFormData = { ...formData };

	function handleSubmit() {
		console.log(formData);
		console.log(originalFormData);
	}

	let formel;
</script>

<div class="card">
	<img src="https://picsum.photos/150" alt="Image_duu" />
	<form on:submit|preventDefault={handleSubmit} id="formEl" bind:this={formel}>
		<label for="name">Name:</label>
		<input required type="text" id="name" bind:value={formData.name} placeholder="Name" />
		<label for="description">Description:</label>
		<input required type="text" id="description" bind:value={formData.description} placeholder="Description" />
		<label for="price">Price:</label>
		<input required type="number" inputmode="numeric" id="price" bind:value={formData.price} placeholder="Price" />
		<button type="submit" disabled={JSON.stringify(formData) === JSON.stringify(originalFormData) || !formel.checkValidity()}>Save</button>
	</form>
</div>

<style>
	.card {
		border: 1px solid #ccc;
		border-radius: 8px;
		padding: 20px;
		text-align: center;
		box-shadow: 0 4px 8px rgba(156, 155, 155, 0.589);
	}

	.card img {
		width: 150px;
		height: 150px;
		border-radius: 8px;
		margin: 0 auto 20px auto;
		display: block;
	}

	.card form {
		display: flex;
		flex-direction: column;
	}

	.card form label {
		text-align: left;
	}

	.card form input {
		margin-bottom: 10px;
		padding: 8px;
		border: 1px solid #ccc;
		border-radius: 4px;
	}

	.card form button {
		padding: 10px 20px;
		background-color: #007bff;
		color: #fff;
		border: none;
		border-radius: 4px;
		transition: background-color 0.3s;
	}

	.card form button:hover:enabled {
		background-color: #0056b3;
	}
	.card form button:disabled {
		background-color: #5c5959;
		cursor: not-allowed;
	}
	/* Chrome, Safari, Edge, Opera */
	input::-webkit-outer-spin-button,
	input::-webkit-inner-spin-button {
		-webkit-appearance: none;
		margin: 0;
	}

	/* Firefox */
	input[type='number'] {
		-moz-appearance: textfield;
	}
</style>
