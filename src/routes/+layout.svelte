<script lang="ts">
	import { i18n } from '$lib/i18n';
	import { ParaglideJS } from '@inlang/paraglide-sveltekit';
	import '../app.css';

	import MatrixEffect from '$lib/components/MatrixEffect.svelte';
	let { children } = $props();
</script>

<ParaglideJS {i18n}>
	<MatrixEffect />
	{@render children()}
</ParaglideJS>
