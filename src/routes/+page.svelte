<script>
	import { goto } from '$app/navigation';
	import { onMount } from 'svelte';

	// Automatische Weiterleitung beim Laden
	onMount(() => {
			goto('/hyperspace');
	});

</script>

<!--<script>-->
<!--	import { onMount } from "svelte";-->
<!--	import { goto } from '$app/navigation';-->

<!--	let script, link;-->
<!--	let isLoaded = false; // Steuerung, ob der Text angezeigt wird-->

<!--	onMount(async () => {-->
<!--		// Lade das JavaScript-Skript-->
<!--		script = document.createElement('script');-->
<!--		script.src = '/src/lib/hyperspace.js'; // Pfad zur Datei-->
<!--		script.async = true;-->

<!--		// Markiere das Skript als geladen, wenn es fertig ist-->
<!--		script.onload = () => checkLoaded();-->
<!--		document.body.appendChild(script);-->

<!--		// Lade das CSS-->
<!--		link = document.createElement('link');-->
<!--		link.rel = 'stylesheet';-->
<!--		link.href = '/src/lib/hyperspace.css';-->

<!--		// Markiere das CSS als geladen, wenn es fertig ist-->
<!--		link.onload = () => checkLoaded();-->
<!--		document.head.appendChild(link);-->

<!--		// Warte, bis das <canvas> verfügbar ist-->
<!--		let canvas;-->
<!--		const checkCanvas = setInterval(() => {-->
<!--			canvas = document.querySelector("canvas");-->
<!--			if (canvas) {-->
<!--				clearInterval(checkCanvas); // Stoppe die Überprüfung-->
<!--				setupCanvas(canvas); // Initialisiere Event-Listener-->
<!--			}-->
<!--		}, 100);-->
<!--	});-->

<!--	// Prüfen, ob Skript und CSS geladen sind-->
<!--	function checkLoaded() {-->
<!--		if (script.readyState === 'complete' || script.readyState === undefined) {-->
<!--			if (link.readyState === 'complete' || link.readyState === undefined) {-->
<!--				isLoaded = true; // Text wird sichtbar-->
<!--			}-->
<!--		}-->
<!--	}-->

<!--	function cleanup() {-->
<!--		// Entferne das Skript und die CSS-Datei-->
<!--		if (script) script.remove();-->
<!--		if (link) link.remove();-->

<!--		// Entferne zusätzlich von hyperspace.js hinzugefügte Elemente oder Styles-->
<!--		const extraElements = document.querySelectorAll('.hyperspace-element, .hyperspace-style');-->
<!--		extraElements.forEach(el => el.remove());-->
<!--	}-->

<!--	// Setup für Event-Listener auf dem Canvas-->
<!--	function setupCanvas(canvas) {-->
<!--		canvas.addEventListener("click", () => {-->
<!--			// Simuliere gedrückt halten (3 Sekunden)-->
<!--			canvas.dispatchEvent(new Event("mousedown"));-->

<!--			// Timer, um das Loslassen nach 3 Sekunden zu simulieren-->
<!--			setTimeout(() => {-->
<!--				canvas.dispatchEvent(new Event("mouseup")); // Simuliere Loslassen-->
<!--			}, 3000); // 3 Sekunden gedrückt halten-->

<!--			// Starte die Weiterleitung nach 5 Sekunden-->
<!--			setTimeout(() => {-->
<!--				cleanup(); // Aufräumen-->
<!--				goto('/home'); // Weiterleitung-->
<!--			}, 5000); // 5 Sekunden insgesamt-->
<!--		});-->
<!--	}-->
<!--</script>-->

<!--<div class="center-text" style:display={isLoaded ? 'block' : 'none'}>-->
<!--	Drücke zum Starten-->
<!--</div>-->
