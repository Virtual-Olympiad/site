<script lang="ts">
	import Navbar from './Navbar.svelte';
</script>

<h1>About</h1>
<section class = "about">
	<article class = "about-founding">
		<h3>Founding</h3>
		<p>Math et al., also known as MEA, was founded in late 2021. Originally solely consisting of the Virtual Olympiad project, it evolved into a full STEM organization in early 2022.</p>
	</article>

	<article class = "about-projects">
		<h3>Virtual Olympiad</h3>
		<p>TCC help with description pls</p>
	</article>
</section>

<style lang="scss">
	@import '../styles/colors';

	.about {
		display: flex;
		flex-direction: column;
		align-items: center;

		> article {
			width: clamp(300px, 60%, 1000px);

			padding: 10px 30px;
			margin-bottom: 30px;

			border-left: 2px $blue-main solid;

			text-align: left;
		}
	}
</style>