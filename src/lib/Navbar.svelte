<script>
	import { goto } from '$app/navigation';
</script>
<nav class={`fixed top-0 left-0 w-full z-50`}>
	<div class="max-w-7xl mx-auto p-4 flex justify-between items-center">
		<a data-sveltekit-reload href="/hyperspace" class="text-2xl font-bold text-yellow-200">Stellar <br> Swords</a>
		<ul class="flex justify-center space-x-4 text-white">
			<li><a href="/home" class="hover:text-red-500">Home</a></li>
			<li><a href="/shop" class="hover:text-red-500">Shop</a></li>
			<li><a href="/contact" class="hover:text-red-500">Contact</a></li>
		</ul>
	</div>
</nav>

<style>
	div {
		font-family: 'Starjhol', sans-serif;
	}
</style>
