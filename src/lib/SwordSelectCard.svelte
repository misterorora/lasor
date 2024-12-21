<script>
	const colors = [
		{ name: "Rot", color: "bg-red-500", video: "/videos/redlaser.mkv" },
		{ name: "Blau", color: "bg-blue-500", video: "/videos/bluelaser.mkv" },
		{ name: "Grün", color: "bg-green-500", video: "/videos/greenlaser.mkv" },
		{ name: "Lila", color: "bg-purple-500", video: "/videos/purplelaser.mkv" },
	];

	let currentVideo = colors[0].video; // Standard: Grün
	let videoElement;

	const changeVideo = (video) => {
		currentVideo = video; // Aktuelles Video aktualisieren
		videoElement.load(); // Video neu laden
	};
</script>

<div class="container mx-auto py-10 space-y-10 text-white">
	<!-- Section 1: Bild links, Text rechts -->
	<div class="flex flex-col p-10 md:flex-row items-center md:items-start">
		<div class="md:w-1/2 flex flex-col justify-center p-20 mb-6 ">
			<video bind:this={videoElement} autoplay loop muted class="rounded-lg">
				<source src={currentVideo}>
				Your browser does not support the video tag.
			</video>
			<!-- Farbauswahl unter dem Video -->
			<div class="flex justify-center space-x-4 m-4">
				{#each colors as { name, color, video }}
					<button
						class={`w-10 h-10 rounded-full ${color} focus:outline-none border-4 border-transparent hover:border-white`}
						on:click={() => changeVideo(video)}
						title={name}
						aria-label="Sword">
					</button>
				{/each}
			</div>
		</div>
		<div class="md:w-1/2 text-center p-20 md:text-left px-6">
			<h2 class="text-2xl font-bold mb-4">Innovation trifft auf Eleganz</h2>
			<p class="">
				Wähle weise junger Padawan. Die Macht ist stark in dir. Doch nur mit dem richtigen Laserschwert wirst du
				zum Jedi-Meister. Unsere Laserschwerter sind nicht nur ein Werkzeug, sondern ein Symbol für die Macht.
				Du kannst die Macht deinen Bedürfnissen anpassen und bis zu 7 Farben wählen.
			</p>
		</div>
	</div>
</div>