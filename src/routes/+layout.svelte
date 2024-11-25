<script>
	import '../app.css';
	let { children } = $props();
</script>

<nav class="bg-gray-800 text-white p-4 shadow-md">
	<div class="container mx-auto flex items-center justify-between">
		<h1 class="text-2xl font-bold">Laserdullies</h1>
		<div class="flex space-x-6">
			<a href="/" class="hover:text-gray-400 transition">Home</a>
			<a href="/shop" class="hover:text-gray-400 transition">Shop</a>
			<a href="/kontact" class="hover:text-gray-400 transition">Kontakt</a>
		</div>
	</div>
</nav>
{@render children()}
