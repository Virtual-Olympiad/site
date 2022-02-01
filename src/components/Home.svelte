<script lang="ts">
	import Navbar from './Navbar.svelte';
</script>

<main>
	<Navbar />
	
	<header>
		<h1>Virtual Olympiad</h1>
		<p class = "header-description">STEM Olympiad Organization aiming to help students learn and have fun</p>
	</header>
	
	<section class = "cards">
		<article class = "card contests-card">
			<h3>VOMO 2022</h3>
			<p>(Probably not) Coming soon...</p>
			<footer>
				<a href = "/contests#Past_Problems">Past Contests >></a>
			</footer>
		</article>
		<article class = "card trainer-card">
			<h3>VOMP - VO Mock Platform</h3>
			<p>Platform for hosting multiplayer mock contests in a competitive style using problems from past contests</p>
			<footer>
				<a href = "/VOMP">Visit >></a>
			</footer>
		</article>
	</section>
</main>

<style lang="scss">
	main {
		text-align: center;
		padding: 1em;	
		margin: 0 auto;
	}

	header {
		.header-description {
			color: #666;
			font-style: italic;
		}
	}

	.cards {
		display: flex;
		align-items: center;
		justify-content: center;

		> .card {
			width: clamp(300px, 30%, 600px);
		}
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>