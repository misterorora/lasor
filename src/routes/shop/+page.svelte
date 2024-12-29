<script>
	import Navbar from '$lib/Navbar.svelte';
	import choose2 from '$lib/images/Choose2.png';
	import { onDestroy, onMount } from 'svelte';

	let audio;

	onMount(() => {
		audio = new Audio('/sounds/ImperialShop.mp3');
		audio.loop = true;
		audio.play();
	});

	onDestroy(() => {
		if (audio) {
			audio.pause();
		}
	});
</script>

<Navbar/>
<div
	class="h-screen w-screen bg-black text-white flex flex-col justify-center items-center"
	style="background-image: url({choose2}); background-size: cover; background-position: center;"
>
	<h1 class="text-4xl font-bold text-center">Coming Soon</h1>
</div>
