<script>
	import Tailwindcss from "./Tailwindcss.svelte";
	import { fly } from "svelte/transition";
	export let name;
	let fruits;
	let dispense = fruit => (fruits = fruits.filter(f => f !== fruit));
	let refill = () => (fruits = ["apple", "banana", "mango"]);
	refill();
</script>

<main class="text-center p-5 overflow-hidden h-full">
		<h1 class="uppercase text-6xl font-hairline text-svelte mb-3">Hello, {name}!</h1>
	<p class="mb-1">
		Visit the
		<a href="https://svelte.dev/tutorial" class="text-blue-500 underline">Svelte tutorial</a>
		to learn how to build Svelte apps.
	</p>
		<p>
		Visit the
		<a href="https://tailwindcss.com/" class="text-blue-500 underline">Tailwind Documentation</a>
		to learn how to work with tailwindcss.
	</p>


<hr class="my-3">
<h2 class="font-semibold mb-2">Pick a Fruit</h2>
<ul class="flex justify-center -mx-1">
	{#each fruits as fruit, index (fruit)}
		<li  
			on:click={dispense(fruit)}
			in:fly="{{ y: 300, duration: 3000 }}"  out:fly="{{ y: -120, duration: 700 }}"
			class="px-1"
		>
			<button
			 class="rounded-md cursor-pointer border p-3 bg-orange-400 hover:bg-orange-300 shadow-md focus:outline-none focus:shadow-outline">
				{fruit}
			</button>
		</li>
		{:else}
		<li class="px-1 absolute">
					<button 
				on:click={refill}
				in:fly="{{ x: -300, duration: 700, delay: 250}}" 
				class="px-3 py-1 border focus:outline-none focus:shadow-outline bg-blue-600 hover:bg-blue-500 text-white rounded-md shadow-md"
		>Refill</button>
		</li>

	{/each}
</ul>

</main>

<style>
</style>