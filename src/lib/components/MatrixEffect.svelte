<script>
	import { onMount } from 'svelte';

	let canvas;
	let ctx;
	let columns;
	let drops = [];
	let columnSettings = [];
	let chars = '0123456789ABCDEF';
	let baseFontSize = 12;

	onMount(() => {
		ctx = canvas.getContext('2d');

		function resizeCanvas() {
			canvas.width = window.innerWidth;
			canvas.height = window.innerHeight;
			columns = Math.floor(canvas.width / baseFontSize);

			columnSettings = Array.from({ length: columns }, () => ({
				fontSize: Math.random() * 14 + 10,
				speed: Math.random() * 0.8 + 0.2,
				opacity: Math.random() * 0.5 + 0.5, // Adjusted for better contrast
				trailLength: Math.floor(Math.random() * 10 + 5)
			}));

			drops = Array.from({ length: columns }, () =>
				Math.floor((Math.random() * canvas.height) / baseFontSize)
			);

			drawStaticBackground();
		}

		function drawStaticBackground() {
			ctx.fillStyle = 'black';
			ctx.fillRect(0, 0, canvas.width, canvas.height);
		}

		function drawMatrix() {
			ctx.fillStyle = 'rgba(0, 0, 0, 0.2)'; // Slightly darker fade
			ctx.fillRect(0, 0, canvas.width, canvas.height);

			for (let i = 0; i < columns; i++) {
				let { fontSize, speed, opacity, trailLength } = columnSettings[i];
				ctx.font = `${fontSize}px monospace`;

				let x = i * baseFontSize;
				let y = drops[i] * fontSize;

				for (let j = 0; j < trailLength; j++) {
					let fadeFactor = j / trailLength;
					let text = chars[Math.floor(Math.random() * chars.length)];
					ctx.fillStyle = `rgba(0, 150, 0, ${opacity * (1 - fadeFactor)})`;
					ctx.fillText(text, x, y - j * fontSize);
				}

				if (y - trailLength * fontSize > canvas.height && Math.random() > 0.975) {
					drops[i] = 0;
				}
				drops[i] += speed;
			}

			// Reset Filter after drawing to avoid blurring other elements
			ctx.filter = 'none';
		}

		resizeCanvas();
		window.addEventListener('resize', resizeCanvas);

		let interval = setInterval(drawMatrix, 50);

		return () => {
			clearInterval(interval);
			window.removeEventListener('resize', resizeCanvas);
		};
	});
</script>

<canvas bind:this={canvas} class="matrix-background"></canvas>

<style>
	canvas {
		position: fixed;
		top: 0;
		left: 0;
		width: 100vw;
		height: 100vh;
		z-index: -1;
		background: black;
		filter: blur(3px); /* Adds a blur effect */
		opacity: 0.8; /* Slight transparency */
	}
</style>
