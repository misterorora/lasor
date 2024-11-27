<script>
	import { onMount } from "svelte";
	import { goto } from '$app/navigation';

	let timeout; // Speichert den Timer
	let holdTimeout; // Timer für das Gedrückthalten
	let redirectTimeout; // Timer für die Weiterleitung

	onMount(async () => {
		// Lade das JavaScript-Skript
		const script = document.createElement('script');
		script.src = '/src/lib/hyperspace.js'; // Pfad zur Datei
		script.async = true;
		document.body.appendChild(script);

		// Lade das CSS
		const link = document.createElement('link');
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
		canvas.addEventListener("mousedown", () => {
			holdTimeout = setTimeout(() => {
				// Simuliere Loslassen nach 2 Sekunden
				canvas.dispatchEvent(new Event("mouseup"));

				// Nach 2 Sekunden Gedrückthalten einen weiteren Timer starten
				redirectTimeout = setTimeout(() => {
					goto('/home'); // Weiterleitung nach zusätzlichen 3 Sekunden
				}, 5000); // 3 Sekunden Verzögerung
			}, 2000); // 2 Sekunden Gedrückthalten
		});

		canvas.addEventListener("mouseup", () => {
			clearTimeout(holdTimeout); // Timer für das Gedrückthalten abbrechen
			clearTimeout(redirectTimeout); // Timer für die Weiterleitung abbrechen
		});

		// Unterstützung für Touch-Geräte
		canvas.addEventListener("touchstart", () => {
			holdTimeout = setTimeout(() => {
				// Simuliere Loslassen nach 2 Sekunden
				canvas.dispatchEvent(new Event("touchend"));

				// Nach 2 Sekunden Gedrückthalten einen weiteren Timer starten
				redirectTimeout = setTimeout(() => {
					goto('/home'); // Weiterleitung nach zusätzlichen 3 Sekunden
				}, 5000); // 3 Sekunden Verzögerung
			}, 2000); // 2 Sekunden Gedrückthalten
		});

		canvas.addEventListener("touchend", () => {
			clearTimeout(holdTimeout); // Timer für das Gedrückthalten abbrechen
			clearTimeout(redirectTimeout); // Timer für die Weiterleitung abbrechen
		});
	}
</script>

<div class="center-text">
	Gedrückt halten zum Starten
</div>

