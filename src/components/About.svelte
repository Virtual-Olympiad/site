<script lang="ts">
</script>

<h1>About</h1>
<section class = "about">
	<article class = "about-founding">
		<h3>Math et Al</h3>
		<p>Math et al, also known as MEA, was founded in late 2021. Originally solely consisting of the Virtual Olympiad project, we evolved into a full STEM organization by early 2022.</p>
		<p>Our goal is to make competitive math (et al) more fun and enjoyable. We host many fun events in math, chess, programming, and more. If you're interested in joining our team or helping out for an event, apply <a href="/apply">here</a>.</p>
	</article>

	<article class = "about-projects">
		<h3>Virtual Olympiad</h3>
		<p>Virtual Olympiad (VO or VOLY) is an online multiplayer practice platform for the AMC and AIME (and more to come!). Host highly customizable practice contests using questions from past contests and compete against your friends. VO not only helps you prepare for the AMC/AIME, but also provides a fun and competitive spin to contest math.</p>
		<p><a href = "/vo">Visit >></a></p>
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

			box-shadow: 3px 3px 3px #999, -1px -1px 3px #eee;

			transition: ease .3s;

			&:hover {
				transform: scale(1.02);
			}
		}
	}
</style>