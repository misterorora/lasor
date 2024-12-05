<script>
	import Navbar from '$lib/Navbar.svelte';
	import choose2 from '$lib/images/Choose2.png';
</script>

<Navbar/>
<div class="h-screen w-screen overflow-y-scroll bg-black text-white" style="background-image: url({choose2})">
	<div class="flex flex-col items-center">
		<img src="https://via.placeholder.com/300" alt="Animation" class="rounded-lg shadow-lg">
		<h1 class="text-4xl font-bold text-center py-10">Shop</h1>
	</div>
</div>