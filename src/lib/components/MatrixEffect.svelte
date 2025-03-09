<script>
	import { onMount } from 'svelte';

	let canvas;
	let ctx;
	let columns;
	let drops = [];
	let columnSettings = []; // Stores size, speed, opacity, and trail length per column
	let chars = '0123456789ABCDEF';
	let baseFontSize = 12; // Smaller base size to fit more lines

	onMount(() => {
		ctx = canvas.getContext('2d');

		function resizeCanvas() {
			canvas.width = window.innerWidth;
			canvas.height = window.innerHeight;
			columns = Math.floor(canvas.width / baseFontSize); // Increase number of columns

			// Generate random sizes, speeds, opacity, and **shorter** trail lengths
			columnSettings = Array.from({ length: columns }, () => ({
				fontSize: Math.random() * 14 + 10, // Random font size (10px - 24px)
				speed: Math.random() * 0.8 + 0.2, // Slower speed (0.2x - 1.0x)
				opacity: Math.random() * 0.6 + 0.4, // Medium opacity (distant ones are more faded)
				trailLength: Math.floor(Math.random() * 10 + 5) // **Balanced streaks (5-15 characters)**
			}));

			// Randomize initial drop positions
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
			ctx.fillStyle = 'rgba(0, 0, 0, 0.15)'; // Fainter clearing for better trails
			ctx.fillRect(0, 0, canvas.width, canvas.height);

			for (let i = 0; i < columns; i++) {
				let { fontSize, speed, opacity, trailLength } = columnSettings[i];
				ctx.font = `${fontSize}px monospace`;

				let x = i * baseFontSize;
				let y = drops[i] * fontSize;

				// Shorter trailing effect
				for (let j = 0; j < trailLength; j++) {
					let fadeFactor = j / trailLength;
					let text = chars[Math.floor(Math.random() * chars.length)];
					ctx.fillStyle = `rgba(0, 150, 0, ${opacity * (1 - fadeFactor)})`; // Fades out as it falls
					ctx.fillText(text, x, y - j * fontSize);
				}

				// Reset after a moderate-length drop
				if (y - trailLength * fontSize > canvas.height && Math.random() > 0.975) {
					drops[i] = 0;
				}
				drops[i] += speed;
			}
		}

		resizeCanvas();
		window.addEventListener('resize', resizeCanvas);

		let interval = setInterval(drawMatrix, 50); // Smooth refresh rate

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
	}
</style>
