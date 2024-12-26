<script>
	import '$lib/starwarsintro.css'
	import { onMount } from 'svelte';

	let showAbspann = false;


	onMount(() => {
		setTimeout(() => {
			showAbspann = true;
		}, 5000);
	})

</script>

<div class="star-wars-intro">

	<!-- Blue Intro Text -->
	<p class="intro-text">
		Wir dürfen präsentieren:
	</p>

	<!-- Logo Image or Text goes in here -->
	<h2 class="main-logo flex flex-col items-center">
		Stellar Swords
	</h2>

	<!-- All Scrolling Content Goes in here -->
	<div class="main-content">

		<div class="title-content">
			<p class="content-header">Die Macht steckt in jedem von uns</p>

			<br>

			<p class="content-body">
				Es vergingen Äonen von Jahren, bis wir endlich die Technologie entwickeln konnten,
				um die Macht in die Hände derer zu legen, die sie verdienen.
				Von nun an herrscht Gleichgewicht in der Galaxis.
				Bist du bereit, die Macht zu spüren?
			</p>

			<p class="content-body">
				Unsere Laserschwerter sind kein Spielzeug, sondern echte Werkzeuge.
				Erlebe die Macht in deinen Händen und werde zum Jedi-Meister.
				Alle Infos findest du auf dieser Webseite!
			</p>

			<!-- button or link or whatever -->
			<a href="/shop" class="space-button">Jetzt Kaufen!</a>

		</div>

	</div>
</div>
<!--{#if showAbspann}-->
<!--	<div class="text-white text-xl text-center items-center absolute">-->
<!--		&lt;!&ndash; Blue Intro Text &ndash;&gt;-->
<!--		Test-->
<!--	</div>-->
<!--{/if}-->
