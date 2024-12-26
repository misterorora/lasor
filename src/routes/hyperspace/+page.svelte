<script>
	import { onMount } from 'svelte';
	import { goto } from '$app/navigation';

	let audio;

	onMount(() => {
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
		canvas.addEventListener('click', () => {
			// Sound abspielen
			if (audio) {
				audio.currentTime = 0; // Zurück zum Anfang, falls bereits gespielt wird
				audio.play();
			}

			canvas.dispatchEvent(new Event('mousedown'));

			setTimeout(() => {
				canvas.dispatchEvent(new Event('mouseup'));
			}, 3000);

			setTimeout(() => {
				if (audio) {
					audio.pause();
				}
				goto('/home');
			}, 5000);
		});
	}
</script>

<div class="center-text text-white">
	Klicke zum Starten
</div>