<script>
	export let name;
</script>

<main class="p-4 mx-auto text-center max-w-xl">
	<h1 class="uppercase text-6xl font-hairline text-svelte">Hello, {name}!</h1>
	<p class="my-2">
		Visit the
		<a href="https://svelte.dev/tutorial" class="text-blue-500 underline">Svelte tutorial</a>
		to learn how to build Svelte apps.
	</p>
		<p>
		Visit the
		<a href="https://tailwindcss.com/" class="text-blue-500 underline">Tailwind Documentation</a>
		to learn how to work with this css framework.
	</p>
</main>

<style global>
  body {
    @apply bg-gray-200 h-screen w-screen min-h-0 min-w-0;
  }
  @tailwind base;
  @tailwind components;
  @tailwind utilities;
</style>