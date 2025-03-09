<script>
	import { onMount } from 'svelte';

	// let message = 'COMING SOON...';
	let message = 'COMING\u00A0SOON...';

	let glitchText = message.split('');

	onMount(() => {
		console.log('Coming Soon Component Loaded!'); // Debugging log
	});
</script>

<div
	class="fixed inset-0 flex flex-col items-center justify-center bg-transparent text-center font-mono text-green-400"
>
	<!-- Main Glitching Title -->
	<h1 class="relative text-4xl font-bold tracking-wider whitespace-nowrap md:text-6xl lg:text-7xl">
		{#each glitchText as char, i}
			<span class="glitch mx-[1px] inline-block" style="animation-delay: {i * 50}ms">
				{char}
			</span>
		{/each}
	</h1>

	<!-- Subtext -->
	<p class="mt-4 text-lg opacity-80 md:text-xl">The system is initializing...</p>

	<!-- Loading Spinner -->
	<div class="mt-6 flex justify-center">
		<div
			class="h-10 w-10 animate-spin rounded-full border-4 border-green-400 border-t-transparent"
		></div>
	</div>
</div>

<style>
	@keyframes glitch {
		0% {
			transform: translate(0, 0);
			opacity: 1;
		}
		20% {
			transform: translate(-2px, 2px);
			opacity: 0.8;
		}
		40% {
			transform: translate(2px, -2px);
			opacity: 0.6;
		}
		60% {
			transform: translate(-3px, 3px);
			opacity: 0.8;
		}
		80% {
			transform: translate(3px, -3px);
			opacity: 1;
		}
		100% {
			transform: translate(0, 0);
			opacity: 1;
		}
	}

	.glitch {
		display: inline-block;
		animation: glitch 0.8s infinite alternate;
	}
</style>
