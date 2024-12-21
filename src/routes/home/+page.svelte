<script lang="ts">
	import Navbar from '$lib/Navbar.svelte';
	import choose2 from '$lib/images/Choose2.png';
	import choose3 from '$lib/images/Choose3.png';
	import download from '$lib/images/Download.png';
	import '$lib/starwarsintro.css'
	import StarWarsIntro from '$lib/StarWarsIntro.svelte';
	import SwordSelectCard from '$lib/SwordSelectCard.svelte';
	import InterviewCard from '$lib/InterviewCard.svelte';
	import { onMount } from 'svelte';

	let images = [
		{ src: choose2, content: StarWarsIntro },
		{ src: choose3, content: SwordSelectCard },
		{ src: download, content: InterviewCard }
	];

	onMount(() => {
		if(document.querySelector("canvas")){document.querySelector("canvas").remove();}
	});
</script>

<style>
    /* Container für Scrollen */
    .h-screen {
        scroll-behavior: smooth; /* Flüssiges Scrollen */
        scroll-snap-type: y mandatory; /* Vertikales Snapping */
        overflow-y: scroll;
    }

    /* Snap-Bereiche */
    .snap-start {
        scroll-snap-align: start;
        scroll-snap-stop: always; /* Verzögertes Snapping */
    }

    /* Optionale Transition für den visuellen Effekt */
    .snap-start {
        transition: transform 0.8s ease, scroll-snap-align 0.8s ease;
    }
</style>

<Navbar />
<div class="h-screen w-screen overflow-y-scroll snap-y snap-mandatory bg-black">
	{#each images as image (image.src)}
		<section
			class="h-full w-full bg-cover bg-center snap-start"
			style="background-image: url({image.src});"
		>
			{#if typeof image.content === 'string'}
				<div class="inset-0 flex justify-center items-center">
					{@html image.content}
				</div>
			{:else}
				<svelte:component this={image.content} />
			{/if}
		</section>
	{/each}
</div>