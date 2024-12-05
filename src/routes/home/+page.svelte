<script lang="ts">
	import Navbar from '$lib/Navbar.svelte';
	import choose2 from '$lib/images/Choose2.png';
	import choose3 from '$lib/images/Choose3.png';
	import download from '$lib/images/Download.png';
	import '$lib/starwarsintro.css'
	import StarWarsIntro from '$lib/StarWarsIntro.svelte';
	import SwordSelectCard from '$lib/SwordSelectCard.svelte';
	import InterviewCard from '$lib/InterviewCard.svelte';

	let images = [
		{ src: choose2, content: StarWarsIntro },
		{ src: choose3, content: SwordSelectCard },
		{ src: download, content: InterviewCard }
	];
</script>

<Navbar/>
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