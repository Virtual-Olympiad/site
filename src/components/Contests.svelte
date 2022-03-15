<script lang="ts">
	interface Contest {
		name: string;
		year: number;
		description?: string;
	}

	const contests: Contest[] = [
		
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
		<h2>CHESSKON</h2> 
		<p>
			CHESSKON is an international chess tournament hosted by Math et Al and FISKON. We have an open section and a U1200 section and great prizes for participants!
		</p>
		<p><a href="/contests/chesskon">Details >></a></p>
		<img class = "contest-poster" src="/CHESSKON.png" alt = "CHESSKON Poster"/>
	</article>

	<section class = "contests-past" id = "Past_Contests">
		<div class = "bar"></div>
		<h2>
			Past Contests
		</h2>

		{#each contests as contest, i}
			<article>
				<h3>{contest.name} {contest.year}</h3>
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

	.contests-current, .contests-past {
		display: flex;
		flex-direction: column;
		align-items: center;

		width: clamp(460px, 40%, 1000px);

		margin: 1em;
		padding: 30px;

		box-shadow: 3px 0px 3px #eee, -3px 0px 3px #eee;

		transition: ease .3s;

		&:hover {
			transform: scale(1.02);
		}
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