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

<div class="container mx-auto py-10 space-y-10 text-white">

	<!-- Section 2: Text links, Bild rechts -->
		<div class="flex flex-col items-center md:items-start md:flex-row-reverse">
			<div
				class={`md:w-1/2 flex justify-center p-20 mb-6 md:mb-0 transition-opacity duration-1000 ${
	        isVisible ? "fade-in" : "opacity-0"
	      }`}
			>
				<img src="https://via.placeholder.com/300" alt="Animation" class="rounded-lg shadow-lg">
			</div>
			<div class="md:w-1/2 text-center p-20 md:text-left ml-10">
				<h2 class="text-2xl font-bold mb-4">Design, das begeistert</h2>
				<p class="">
					Unser Design ist einzigartig und wird dich begeistern. Wir haben uns von den besten Jedi-Meistern inspirieren lassen und
					unsere Laserschwerter so gestaltet, dass sie nicht nur gut aussehen, sondern auch gut in der Hand liegen. Die wichtigsten
					Fragen rund um unser Konzept beantwortet dir unser Interview mit dem Gründer.
				</p>
			</div>
		</div>
</div>