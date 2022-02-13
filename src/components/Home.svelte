<script lang="ts">
</script>

<header>
	<div class = "header-title">
		<h1>Math et al.</h1>
		<p class = "header-description">STEM organization aiming to help students learn and have fun</p>
	</div>
</header>

<section class = "cards">
	<article class = "card">
		<h3>MEA Contest 2022</h3>
		<p>(Probably not) Coming soon...</p>
		<footer>
			<a href = "/contests#Past_Problems">Past Contests >></a>
		</footer>
	</article>
	<article class = "card">
		<h3>Virtual Olympiad</h3>
		<p>Platform for hosting competitive multiplayer mock contests</p>
		<footer>
			<a href = "/vo">Visit >></a>
		</footer>
	</article>
</section>

<style lang="scss">
	@import '../styles/colors';

	header {
		display: flex;
		align-items: center;
		justify-content: center;

		height: clamp(250px, 50vh, 500px);

		.header-description {
			color: #666;
			font-style: italic;
		}
	}

	.cards {
		display: flex;
		align-items: center;
		justify-content: center;

		height: 200px;

		> .card {
			display: flex;
			flex-direction: column;
			align-items: center;
			justify-content: flex-start;

			height: 100%;
			width: clamp(300px, 30%, 600px);
			margin: 20px;
			padding: 10px 0;

			border-top: 2px $blue-main solid;
		}
	}
</style>