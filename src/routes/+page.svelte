<script lang="ts">
	import ComingSoon from '$lib/components/ComingSoon.svelte';
	import SkillCard from '$lib/components/SkillCard.svelte';
</script>

<!-- <ComingSoon /> -->

<h2
	class="relative text-center text-4xl font-extrabold tracking-widest text-[#10B981] uppercase drop-shadow-[2px_2px_0px_#0f3d21]
           transition-all duration-300
           before:absolute before:-top-1 before:-left-1 before:z-[-1]
           before:scale-[1.05] before:text-[#0b2916] before:opacity-80
           before:blur-sm before:content-[attr(data-title)] hover:before:-top-1 hover:before:-left-1
           hover:before:opacity-100 hover:before:blur-none md:text-6xl
           md:drop-shadow-[4px_4px_0px_#0f3d21] md:before:-top-2 md:before:-left-2"
	data-title="My Tech Stack"
>
	My Tech Stack
</h2>

<div class="flex flex-wrap justify-center gap-6 p-4">
	<SkillCard
		title="CUDA Programming"
		description="Optimized GPU computing with CUDA for high-performance applications."
		icon="/logos/cuda.png"
		link="https://github.com/skimondo/linear-regression-cuda"
	/>

	<SkillCard
		title="Intel TBB"
		description="Multithreading and parallel execution using Intel's Threading Building Blocks."
		icon="/logos/logo-oneapi.webp"
		link="https://github.com/skimondo/particle-acceleration-tbb"
	/>

	<SkillCard
		title="Machine Learning"
		description="Training deep learning models with PyTorch & TensorFlow."
		icon="logos/spark-logo-rev.svg"
		link="https://github.com/your-ml-project"
	/>
	<SkillCard
		title="Neo4j"
		description="Graph database optimized for connected data and complex queries."
		icon="/logos/neo4j-white.webp"
		link="https://github.com/skimondo/Neo4j"
	/>
</div>
