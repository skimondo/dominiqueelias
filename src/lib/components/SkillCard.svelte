<script>
	export let title = 'CUDA Programming';
	export let description = 'Optimized GPU computing with CUDA for high-performance applications.';
	export let icon = '/icons/cuda.svg'; // Path to the skill icon/image
	export let link = 'https://github.com/your-repo'; // GitHub or project link
</script>

<a
	href={link}
	target="_blank"
	rel="noopener noreferrer"
	class="group perspective-1000 relative flex w-full max-w-lg transform items-center space-x-6 rounded-xl
            border border-green-400 bg-black p-5 shadow-lg
            transition-all duration-300 hover:scale-105 hover:rotate-2 hover:bg-green-900/10 hover:shadow-green-500/20"
>
	<!-- Icon/Image Container with 3D Effect -->
	<div
		class="flex h-20 w-20 flex-shrink-0 items-center justify-center rounded-lg bg-green-900/10
                transition-all duration-300 ease-out group-hover:scale-110 group-hover:rotate-[15deg]"
	>
		<img
			src={icon}
			alt={title}
			class="h-16 w-16 object-contain transition-transform duration-300 group-hover:scale-130"
		/>
	</div>

	<!-- Text Content -->
	<div class="flex-1">
		<h2 class="text-xl font-bold text-green-400 transition-all group-hover:text-green-300">
			{title}
		</h2>
		<p class="text-sm text-gray-400 transition-all group-hover:text-gray-200">{description}</p>
	</div>

	<!-- Floating Glow Effect -->
	<div
		class="absolute inset-0 rounded-xl bg-green-500 opacity-10 blur-xl transition-all duration-300 group-hover:opacity-20"
	></div>
</a>
