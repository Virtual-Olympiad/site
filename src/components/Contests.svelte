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

		{
			name: "VOMO",
			year: 2021,
			description: "Totally exists"
		}
	];

	contests.sort((a, b) => {
		if (a.year == b.year){
			return a.name.localeCompare(b.name, 'en', { sensitivity: 'base' });;
		}

		return b.year - a.year;
	});
</script>

<main>
	<Navbar />

	<h1>Contests</h1>

	<section class = "contests-current">
		<h2>The Virtual Open Mathematical Olympiad</h2> 
		<p>
			Pausechamp?
		</p>
		<img height = "100px" title = "Not Copium" alt = "Copium" src = "https://gumlet.assettype.com/afkgaming%2F2021-08%2F79649079-d0e7-4acd-853b-6a2b92797da3%2Fcopium_png.png?format=auto"/>
	</section>
	
	<section class = "contests-past" id = "Past_Problems">
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
</main>

<style>
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

	section {
		padding: 30px;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>