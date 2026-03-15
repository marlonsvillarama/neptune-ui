<script>
	import '../style/layout.css';
	import favicon from '$lib/assets/favicon.svg';
	import Header from '@/components/global/header.svelte';

	let { children } = $props();
</script>

<svelte:head><link rel="icon" href={favicon} /></svelte:head>

<Header />

<main class="container py-6">
	{@render children()}
</main>
