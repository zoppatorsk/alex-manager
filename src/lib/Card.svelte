<script>
	export let formData;
	let originalFormData = { ...formData };

	function handleSubmit() {}
</script>

<div class="card">
	<img src="https://picsum.photos/150" alt="Image_duu" />
	<form on:submit|preventDefault={handleSubmit}>
		<label for="name">Name:</label>
		<input type="text" id="name" bind:value={formData.name} placeholder="Name" />
		<label for="description">Description:</label>
		<input type="text" id="description" bind:value={formData.description} placeholder="Description" />
		<label for="price">Price:</label>
		<input type="text" id="price" bind:value={formData.price} placeholder="Price" />
		<button type="button" disabled={JSON.stringify(formData) === JSON.stringify(originalFormData)}>Save</button>
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
</style>
