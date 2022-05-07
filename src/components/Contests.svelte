<script lang="ts">
	interface Contest {
		name: string;
		year: number;
		description?: string;
		link?: string;
	}

	const contests: Contest[] = [
		{
			name: "CHESSKON",
			year: 2022,
			description: "A free to join international chess tournament hosted by Math et Al and FISKON. Had both an Open section and a U1200 section and more than $100 in prizes.",
			link: "/contests/chesskon"
		}
	];

	contests.sort((a, b) => {
		if (a.year == b.year){
			return a.name.localeCompare(b.name, 'en', { sensitivity: 'base' });;
		}

		return b.year - a.year;
	});
</script>

<svelte:head>
    <meta name="description" content="Math et al's contests and events">
</svelte:head>

<h1>Contests & Events</h1>

<section class = "contests">
	<article class = "contests-current">
		<div class = "bar"></div>
		<h2>MEAAC 1</h2> 
		<p>
			Our first anniversary Math + Physics contest featuring high quality original problems on contest math and physics! Participate in teams up to 2.
		</p>
		<p><a href="/contests/meaac">Details >></a></p>
	</article>

	<section class = "contests-past" id = "Past_Contests">
		<div class = "bar"></div>
		<h2>
			Past Contests
		</h2>

		{#each contests as contest, i}
			<article>
				<a href={contest.link}><h3>{contest.name} {contest.year}</h3></a>
				<p>{contest.description}</p>
			</article>
		{/each}

		{#if contests.length == 0}
		<p>More to come...</p>
		{/if}
	</section>
</section>

<style lang="scss">
	@import '../../styles/colors';

	.contests {
		display: flex;
		flex-wrap: wrap;
		justify-content: center;

		width: 100%;

		padding: 1em;
	}

	.contests-current, .contests-past, article{
		display: flex;
		flex-direction: column;
		align-items: center;

		margin: 1em;
		padding: 30px;

		box-shadow: 3px 0px 3px #eee, -3px 0px 3px #eee;

		transition: ease .3s;

		&:hover {
			transform: scale(1.02);
		}
	}

	.contests-current, .contests-past {
		width: clamp(460px, 40%, 1000px);
	}

	.contest-poster {
		width: 100%;
		max-width: 500px;
	}

	.bar {
		width: 50px;

		border-top: 2px $blue-main solid;
	}

	@media (max-width: 1024px) {
		.contests-current, .contests-past{
			width: clamp(300px, 80%, 1000px);
		}
	}
</style>