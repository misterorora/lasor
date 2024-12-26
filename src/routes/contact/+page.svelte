<script>
	import Navbar from '$lib/Navbar.svelte';
	import choose3 from '$lib/images/Choose3.png';
</script>

<Navbar/>
<div class="h-screen w-screen flex justify-center items-center bg-black text-white" style="background-image: url({choose3}); background-size: cover; background-position: center;">
	<div class="bg-gray-800 bg-opacity-90 p-8 rounded-lg shadow-lg text-center">
		<h1 class="text-3xl font-bold mb-4">Kontaktiere Uns</h1>
		<p class="text-lg mb-6">Hast du Fragen? Wir sind hier, um zu helfen!</p>

		<div class="flex flex-col gap-4">
			<div>
				<p class="text-sm font-semibold">E-Mail:</p>
				<a href="mailto:stellar@swords.de" class="text-blue-400 hover:underline">stellar@swords.de</a>
			</div>

			<div>
				<p class="text-sm font-semibold">Telefon:</p>
				<a href="tel:+491234567890" class="text-blue-400 hover:underline">+49 123 456 7890</a>
			</div>

			<div>
				<p class="text-sm font-semibold">Adresse:</p>
				<p class="text-gray-300">Stellar Swords GmbH<br>Galaxy Avenue 42<br>12345 Star City</p>
			</div>
		</div>
	</div>
</div>