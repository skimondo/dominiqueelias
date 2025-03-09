<script>
	let isOpen = false;

	function toggleMenu() {
		isOpen = !isOpen;
	}
</script>

<nav class="fixed top-0 left-0 z-50 w-full border-b border-[#10B981] bg-black shadow-md">
	<div class="mx-auto flex max-w-6xl items-center justify-between px-6 py-4">
		<!-- Brand / Logo -->
		<a href="/" class="text-2xl font-bold tracking-widest text-[#10B981]">DominiqueElias</a>

		<!-- Desktop Links -->
		<div class="hidden space-x-6 md:flex">
			<a href="#about" class="text-[#10B981] transition-all duration-300 hover:text-[#34D399]"
				>About</a
			>
			<a href="#skills" class="text-[#10B981] transition-all duration-300 hover:text-[#34D399]"
				>Skills</a
			>
			<a href="#projects" class="text-[#10B981] transition-all duration-300 hover:text-[#34D399]"
				>Projects</a
			>
			<a href="#contact" class="text-[#10B981] transition-all duration-300 hover:text-[#34D399]"
				>Contact</a
			>
		</div>

		<!-- Mobile Menu Button -->
		<button class="text-[#10B981] focus:outline-none md:hidden" on:click={toggleMenu}>
			<svg
				class="h-8 w-8"
				fill="none"
				stroke="currentColor"
				viewBox="0 0 24 24"
				xmlns="http://www.w3.org/2000/svg"
			>
				<path
					stroke-linecap="round"
					stroke-linejoin="round"
					stroke-width="2"
					d="M4 6h16M4 12h16m-7 6h7"
				></path>
			</svg>
		</button>
	</div>

	<!-- Mobile Menu -->
	{#if isOpen}
		<div class="space-y-4 border-t border-[#10B981] bg-black p-4 md:hidden">
			<a
				href="#about"
				class="text-[#10B981] transition-all duration-300 hover:text-[#34D399]"
				on:click={toggleMenu}>About</a
			>
			<a
				href="#skills"
				class="text-[#10B981] transition-all duration-300 hover:text-[#34D399]"
				on:click={toggleMenu}>Skills</a
			>
			<a
				href="#projects"
				class="text-[#10B981] transition-all duration-300 hover:text-[#34D399]"
				on:click={toggleMenu}>Projects</a
			>
			<a
				href="#contact"
				class="text-[#10B981] transition-all duration-300 hover:text-[#34D399]"
				on:click={toggleMenu}>Contact</a
			>
		</div>
	{/if}
</nav>
