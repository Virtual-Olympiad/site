<script lang="ts">
	import Navbar from './Navbar.svelte';
</script>

<main>
	<Navbar />

	<h1>About</h1>
	<section class = "about">
		<article class = "about-founding">
			<h3>Founding</h3>
			<p>Virtual Olympiad, also known as VO or VOLY, was founded in late 2021. It was orignally solely a Mock Platform, now known as the VOMP.</p>
			<p>In early 2022, VO became a full STEM organization and now creates various tools to help STEM Olympians learn and have fun.</p>
		</article>

		<article class = "about-projects">
			<h3>VOMP</h3>
			<p>Failure slacks off for months then finally finishes random project that totalled 5 likes on math forum.</p>
		</article>
	</section>
</main>

<style lang="scss">
	main {
		text-align: center;
		padding: 1em;	
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	.about {
		display: flex;
		flex-direction: column;
		align-items: center;

		> article {
			width: clamp(300px, 60%, 1000px);
			padding: 30px;
		}
		
	}
	

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>