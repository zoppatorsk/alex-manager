<script>
	// import svelteLogo from './assets/svelte.svg';
	// import viteLogo from '/vite.svg';

	import Card from './lib/Card.svelte';
	const mockData = [
		{
			id: 1,
			name: 'Product 1',
			price: 1099, // Representing 10.99 as 1099 cents
			description: 'Description for Product 1',
			imageUrl: 'https://picsum.photos/150',
		},
		{
			id: 2,
			name: 'Product 2',
			price: 1999, // Representing 19.99 as 1999 cents
			description: 'Description for Product 2',
			imageUrl: 'https://picsum.photos/150',
		},
		{
			id: 3,
			name: 'Product 3',
			price: 2999, // Representing 29.99 as 2999 cents
			description: 'Description for Product 3',
			imageUrl: 'https://picsum.photos/150',
		},
		// Add more mock data objects as needed
	];

	console.log(mockData);
</script>

<main>
	<h1>Hej babberiba</h1>
	<div class="box-wrapper">
		{#each mockData as formData}
			<Card {formData}></Card>
		{/each}
	</div>
</main>

<style>
	.box-wrapper {
		display: grid;
		grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); /* Adjust the column width as needed */
		grid-gap: 20px; /* Adjust the gap between grid items */
	}
</style>
