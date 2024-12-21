<script>
	import { onMount } from "svelte";
	import { goto } from '$app/navigation';

	let isLoaded = false;

	onMount(() => {
		const checkCanvas = setInterval(() => {
			const canvas = document.querySelector("canvas");
			if (canvas) {
				clearInterval(checkCanvas);
				setupCanvas(canvas);
			}
		}, 100);
	});

	function setupCanvas(canvas) {
		canvas.addEventListener("click", () => {
			canvas.dispatchEvent(new Event("mousedown"));

			setTimeout(() => {
				canvas.dispatchEvent(new Event("mouseup"));
			}, 3000);

			setTimeout(() => {
				goto('/home');
			}, 5000);
		});
	}
</script>

<div class="center-text text-white" >
	Klicke zum Starten
</div>
