<script>
	import { onMount } from "svelte";

	let isVisible = false;

	onMount(() => {
		isVisible = true;
	});
</script>

<style>
    @keyframes fadeIn {
        from {
            opacity: 0;
            transform: translateY(20px);
        }
        to {
            opacity: 1;
            transform: translateY(0);
        }
    }

    .fade-in {
        animation: fadeIn 1s ease-out;
    }
</style>

<div class="container mx-auto py-10 space-y-10">
	<!-- Section 1: Bild links, Text rechts -->
	<div class="flex flex-col md:flex-row items-center md:items-start">
		<div
			class={`md:w-1/2 flex justify-center mb-6 md:mb-0 transition-opacity duration-1000 ${
        isVisible ? "fade-in" : "opacity-0"
      }`}
		>
			<img src="https://via.placeholder.com/300" alt="Laserschwert" class="rounded-lg shadow-lg">
		</div>
		<div class="md:w-1/2 text-center md:text-left px-6">
			<h2 class="text-2xl font-bold mb-4">Innovation trifft auf Eleganz</h2>
			<p class="text-gray-700">
				Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed non risus. Suspendisse lectus tortor,
				dignissim sit amet, adipiscing nec, ultricies sed, dolor. Cras elementum ultrices diam.
			</p>
		</div>
	</div>

	<!-- Section 2: Text links, Bild rechts -->
	<div class="flex flex-col items-center md:items-start md:flex-row-reverse">
		<div
			class={`md:w-1/2 flex justify-center mb-6 md:mb-0 transition-opacity duration-1000 ${
        isVisible ? "fade-in" : "opacity-0"
      }`}
		>
			<img src="https://via.placeholder.com/300" alt="Animation" class="rounded-lg shadow-lg">
		</div>
		<div class="md:w-1/2 text-center md:text-left px-6">
			<h2 class="text-2xl font-bold mb-4">Design, das begeistert</h2>
			<p class="text-gray-700">
				Phasellus fermentum in, dolor. Pellentesque facilisis. Nulla imperdiet sit amet magna. Vestibulum dapibus,
				mauris nec malesuada fames ac turpis velit, rhoncus eu, luctus et interdum adipiscing wisi. Aliquam erat ac ipsum.
			</p>
		</div>
	</div>

	<!-- Section 3: Bild links, Text rechts -->
	<div class="flex flex-col md:flex-row items-center md:items-start">
		<div
			class={`md:w-1/2 flex justify-center mb-6 md:mb-0 transition-opacity duration-1000 ${
        isVisible ? "fade-in" : "opacity-0"
      }`}
		>
			<img src="https://via.placeholder.com/300" alt="Laserschwert" class="rounded-lg shadow-lg">
		</div>
		<div class="md:w-1/2 text-center md:text-left px-6">
			<h2 class="text-2xl font-bold mb-4">Die Zukunft ist hier</h2>
			<p class="text-gray-700">
				Donec nec justo eget felis facilisis fermentum. Aliquam porttitor mauris sit amet orci.
				Aenean dignissim pellentesque felis. Morbi in sem quis dui placerat ornare.
			</p>
		</div>
	</div>
</div>
