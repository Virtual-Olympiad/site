<script lang="ts">
	import Navbar from './Navbar.svelte';

	interface Member {
		name: string;
		country?: string;
	}

	const members: Member[] = [
		{name: "Polarity", country: "Canada"},
		{name: "TheCelestialCube", country: "Canada"},
		{name: "BariumLanthanum", country: "Canada"},
		{name: "Jeffrey Li", country: "Canada"},
		{name: "Void", country: "India"},
		{name: "Zephyr", country: "USA"}
	];

	members.sort((a, b) => {
		return a.name.localeCompare(b.name, 'en', { sensitivity: 'base' });
	})
</script>

<main>
	<Navbar />

	<h1>VOLY Team</h1>

	<section class = "members">
		<ul>
			{#each members as member, i}
				<li>{member.name}, {member.country}</li>
			{/each}
		</ul>
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

	.members {
		padding: 30px;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>