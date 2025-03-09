<script>
	export let text = 'My Tech Stack'; // Customizable title
</script>

<div class="title-card">
	{text}
</div>

<style>
	.title-card {
		width: 100%;
		max-width: 100vw; /* Prevents horizontal overflow */
		padding: 1.5rem 0;
		text-align: center;
		font-size: clamp(1.5rem, 5vw, 2.5rem); /* Adjusts font size based on screen width */
		font-weight: 900;
		text-transform: uppercase;
		color: #10b981; /* Green Matrix theme */
		background: rgba(0, 0, 0, 0.8); /* Dark background for contrast */
		border-top: 4px solid #10b981;
		border-bottom: 4px solid #10b981;
		box-shadow: 0px 4px 10px rgba(16, 185, 129, 0.3);
		position: relative;
		overflow: hidden; /* Ensures no horizontal scroll */
		white-space: nowrap; /* Prevents wrapping */
	}

	/* Glow effect */
	.title-card::before {
		content: '';
		position: absolute;
		top: 0;
		left: 50%;
		width: 50%;
		height: 100%;
		background: rgba(16, 185, 129, 0.1);
		transform: skewX(-10deg);
		z-index: -1;
	}

	.title-card::after {
		content: '';
		position: absolute;
		bottom: -4px;
		left: 0;
		width: 100%;
		height: 4px;
		background: linear-gradient(90deg, transparent, #10b981, transparent);
	}

	/* Responsive behavior */
	@media (max-width: 600px) {
		.title-card {
			font-size: 1.5rem; /* Reduce font size for smaller screens */
			padding: 1rem 0;
		}
	}
</style>
