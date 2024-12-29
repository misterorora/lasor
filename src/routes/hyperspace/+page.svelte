<script>
	import { onMount } from 'svelte';
	import { goto } from '$app/navigation';

	let audio;

	onMount(() => {
		const existingStyles = document.querySelector('link[href="/src/hyperspace.css"]');
		const existingScript = document.querySelector('script[src="/src/hyperspace.js"]');
		if (existingStyles) existingStyles.remove();
		if (existingScript) existingScript.remove();

		if (!existingStyles) {
			const link = document.createElement('link');
			link.rel = 'stylesheet';
			link.href = '/src/hyperspace.css';
			document.head.appendChild(link);
		}

		if (!existingScript) {
			const script = document.createElement('script');
			script.src = '/src/hyperspace.js';
			script.async = true;
			document.head.appendChild(script);
		}

		// Nach 3 Sekunden die Sichtbarkeit ändern
		setTimeout(() => {
			isLoaded = true;
		}, 100);

		const checkCanvas = setInterval(() => {
			const canvas = document.querySelector('canvas');
			if (canvas) {
				clearInterval(checkCanvas);
				setupCanvas(canvas);
			}
		}, 100);

		// Audio-Element erstellen und Pfad anpassen!!!
		audio = new Audio('/HyperdriveSoundShort.mp3'); // Korrekter Pfad!
		audio.preload = 'auto'; // Audio vorladen
	});

	function setupCanvas(canvas) {
		// Sound vorbereiten
		const audio = new Audio('/sounds/hyperdrive_effect.mp3');

		canvas.addEventListener("click", () => {
			// Sound abspielen
			audio.play();

			// Simuliere gedrückt halten (3 Sekunden)
			canvas.dispatchEvent(new Event("mousedown"));

			setTimeout(() => {
				canvas.dispatchEvent(new Event('mouseup'));
			}, 3000);

			// Starte die Weiterleitung nach 6 Sekunden
			setTimeout(() => {
				if (audio) {
					audio.pause();
				}
				goto('/home');
			}, 6000);
		});
	}

</script>

{#if isLoaded}
<div class="center-text text-white">
	Klicke zum Starten
</div>
{/if}

<style>
::-webkit-scrollbar {
		display: none;
}

html {
		scrollbar-width: none; /* Für Firefox */
		-ms-overflow-style: none; /* Für Internet Explorer */
}
</style>