<script lang="ts">
	import Navbar from './Navbar.svelte';

	interface Contest {
		name: string;
		year: number;
		description?: string;
	}

	const contests: Contest[] = [
		{
			name: "UNMC",
			year: 2022,
			description: "Threetris!"
		},
	];

	contests.sort((a, b) => {
		if (a.year == b.year){
			return a.name.localeCompare(b.name, 'en', { sensitivity: 'base' });;
		}

		return b.year - a.year;
	});
</script>

<h1>Contests</h1>

<section class = "contests-current">
	<div class = "bar"></div>
	<h2>Math et al. Contest 2022</h2> 
	<p>
		Pausechamp?
	</p>
	<img height = "100px" title = "Not Copium" alt = "Copium" src = "https://gumlet.assettype.com/afkgaming%2F2021-08%2F79649079-d0e7-4acd-853b-6a2b92797da3%2Fcopium_png.png?format=auto"/>
</section>

<section class = "contests-past" id = "Past_Problems">
	<div class = "bar"></div>
	<h2>
		Past Problems
	</h2>

	{#each contests as contest, i}
		<article>
			<h3>{contest.name} {contest.year}</h3>
			<p>{contest.description}</p>
		</article>
	{/each}
</section>

<style lang="scss">
	@import '../styles/colors';

	section {
		padding: 30px;
	}

	.contests-current, .contests-past{
		display: flex;
		flex-direction: column;
		align-items: center;

		width: clamp(300px, 60%, 1000px);
	}

	.bar {
		width: 50px;

		border-top: 2px $blue-main solid;
	}
</style>