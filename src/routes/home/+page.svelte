<script lang="ts">
	import Navbar from '$lib/Navbar.svelte';
	import choose2 from '$lib/images/Choose2.png';
	import choose3 from '$lib/images/Choose3.png';
	import download from '$lib/images/Download.png';

	let images = [
		choose2,
		choose3,
		download
	];
</script>

<Navbar/>
<div class="h-screen w-screen overflow-y-scroll snap-y snap-mandatory bg-black">
	{#each images as image (image)}
		<section
			class="h-full w-full bg-cover bg-center snap-start"
			style="background-image: url({image});"
		></section>
	{/each}
</div>