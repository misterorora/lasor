<script>
	import { onMount } from "svelte";
	import { goto } from '$app/navigation';

	let script, link;

	onMount(async () => {
		// Lade das JavaScript-Skript
		script = document.createElement('script');
		script.src = '/src/lib/hyperspace.js'; // Pfad zur Datei
		script.async = true;
		document.body.appendChild(script);

		// Lade das CSS
		link = document.createElement('link');
		link.rel = 'stylesheet';
		link.href = '/src/lib/hyperspace.css';
		document.head.appendChild(link);

		// Warte, bis das <canvas> verfügbar ist
		let canvas;
		const checkCanvas = setInterval(() => {
			canvas = document.querySelector("canvas");
			if (canvas) {
				clearInterval(checkCanvas); // Stoppe die Überprüfung
				setupCanvas(canvas); // Initialisiere Event-Listener
			}
		}, 100);
	});

	// Setup für Event-Listener auf dem Canvas
	function setupCanvas(canvas) {
		canvas.addEventListener("click", () => {
			// Simuliere gedrückt halten (3 Sekunden)
			canvas.dispatchEvent(new Event("mousedown"));

			// Timer, um das Loslassen nach 3 Sekunden zu simulieren
			setTimeout(() => {
				canvas.dispatchEvent(new Event("mouseup")); // Simuliere Loslassen
			}, 3000); // 3 Sekunden gedrückt halten

			// Starte die Weiterleitung nach 5 Sekunden
			setTimeout(() => {
				if (script) script.remove();
				if (link) link.remove();
				goto('/home'); // Weiterleitung
			}, 8000); // 5 Sekunden insgesamt
		});
	}
</script>

<div class="center-text">
	Drücke zum Starten
</div>

