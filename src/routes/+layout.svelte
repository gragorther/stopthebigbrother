<script lang="ts">
	import { injectAnalytics } from '@vercel/analytics/sveltekit';
	injectAnalytics();
	import { injectSpeedInsights } from '@vercel/speed-insights/sveltekit';
	injectSpeedInsights();
	import '../app.css';
	import ResultBox from '$lib/ResultBox.svelte';
	import DualImage from '$lib/DualImage.svelte';
	import NavButton from '$lib/NavButton.svelte';
	import ClickableButton from '$lib/ClickableButton.svelte';
	interface Props {
		children?: import('svelte').Snippet;
	}
	let { children }: Props = $props();
</script>

<!-- Centralized container for consistent scaling -->
<div class="flex flex-col min-h-screen pb-16">
	<!-- Navigation Bar -->
	<nav class="rounded-lg m-4">
		<div class="container mx-auto px-2 sm:px-8 lg:max-w-4xl flex flex-wrap justify-center gap-4">
			<div class="flex items-center justify-center gap-0">
				<img
					src="/favicon.png"
					alt="This site's logo, an eye"
					class="ml-1 mr-0.5 object-fill h-11 w-11"
				/>
				<NavButton href="/">Home</NavButton>
				<NavButton href="/contact">Contact</NavButton>
				<NavButton href="/blog">Blog</NavButton>
				<img
					src="/favicon.png"
					alt="This site's logo, an eye"
					class="mr-1 ml-0.5 object-fill h-11 w-11"
				/>
			</div>
		</div>
	</nav>

	<!-- Main Content Section -->
	<main class="flex-grow">
		<div class="container mx-auto px-4 sm:px-8 lg:max-w-4xl">
			{@render children?.()}
		</div>
	</main>

	<!-- Footer Section -->
	<footer class="container mx-auto px-4 sm:px-8 lg:max-w-4xl">
		<div class="flex justify-center text-sm pb-8 mt-4">
			<ResultBox>
				The source code for this website is available on my
				<ClickableButton href="https://github.com/gragorther/stopthebigbrother">
					<DualImage imgSrc="/Octicons-mark-github.svg">GitHub</DualImage>
				</ClickableButton> page.
			</ResultBox>
		</div>
	</footer>
</div>

<!-- PostCSS Styling for Consistent Scaling -->
<style lang="postcss">
	@tailwind base;

	@layer base {
		.shared-properties {
			@apply bg-gradient-to-r text-transparent bg-clip-text font-extrabold mx-auto my-5 text-center p-2;
		}
	}
	:global(body) {
		@apply bg-zinc-900 text-white font-mono;
		background-image: url('/coolbg.png');
		background-size: 200px;
	}

	:global(p) {
		@apply text-lg my-4 mx-auto text-justify;
		max-width: 800px;
	}

	:global(h1) {
		@apply shared-properties text-4xl sm:text-5xl lg:text-6xl text-red-500 leading-relaxed;
	}

	:global(h2) {
		@apply shared-properties text-3xl sm:text-4xl lg:text-5xl from-orange-500 to-pink-700 leading-relaxed;
	}

	:global(a) {
		@apply text-lg sm:text-xl text-blue-600 hover:text-blue-400;
	}

	/* Navigation Buttons */
	:global(.nav-button) {
		@apply border-solid border-white border-2 rounded-sm bg-red-600 p-2 text-center hover:bg-red-400 text-white;
		min-width: 140px;
	}

	/* Responsive Button Layout */

	/* Centralize List Items */
	:global(ul) {
		@apply flex flex-row items-center justify-center;
	}

	/* Scale List Items Properly */
	:global(li) {
		@apply mx-4 text-lg;
	}
</style>
