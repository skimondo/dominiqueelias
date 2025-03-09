<script lang="ts">
	import ThreeDTitle from '$lib/components/3DTitle.svelte';
	import SkillCard from '$lib/components/SkillCard.svelte';
</script>

<ThreeDTitle text="Techs I've worked with" />

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
		title="OpenMP"
		description="API for multi-platform shared memory parallel programming in C, C++, and Fortran."
		icon="/logos/openmp.png"
		link="https://github.com/skimondo/vantage-point-tree-open-mp"
	/>

	<SkillCard
		title="MPI (Message Passing Interface)"
		description="Standard for distributed memory parallel computing in C, C++, and Fortran."
		icon="/logos/openmpi.png"
		link="https://github.com/skimondo/mpi-performance"
	/>

	<SkillCard
		title="Machine Learning"
		description="Training deep learning models with Spark ML."
		icon="logos/spark-logo-rev.svg"
		link="https://github.com/skimondo/hadoop-spark"
	/>
	<SkillCard
		title="Neo4j"
		description="Graph database optimized for connected data and complex queries."
		icon="/logos/neo4j-white.webp"
		link="https://github.com/skimondo/Neo4j"
	/>

	<SkillCard
		title="Coq Proof Assistant"
		description="Formal verification and theorem proving with dependent types."
		icon="/logos/coq.png"
		link="https://github.com/skimondo/linear-lambda-calculus"
	/>

	<SkillCard
		title="Modern Java"
		description="Building high-performance applications with Java 17+ features like Records, Streams, and Virtual Threads."
		icon="/logos/java.png"
		link="https://gitlab.info.uqam.ca/elias.dominique/tp2-mgl7460"
	/>

	<SkillCard
		title="Drools with Java"
		description="Business rule management system (BRMS) for Java-based applications."
		icon="/logos/drools.png"
		link="https://gitlab.info.uqam.ca/elias.dominique/tp3-mgl7460"
	/>

	<SkillCard
		title="Python"
		description="Versatile programming language for data science, AI, automation, and web development."
		icon="/logos/python.webp"
		link="https://gitlab.info.uqam.ca/elias.dominique/tp1-mgl7460"
	/>

	<SkillCard
		title="C / C++"
		description="High-performance programming languages for systems, embedded, and parallel computing."
		icon="/logos/cpp.png"
		link="https://gitlab.info.uqam.ca/elias.dominique/inf3135-hiver2023-tp3"
	/>
</div>
