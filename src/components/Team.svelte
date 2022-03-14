<script lang="ts">
	import Navbar from './Navbar.svelte';

	type Role = 'Developer' | 'Problem Writer' | 'Testsolver' | 'Outreach';

	interface Member {
		name: string;
		roles: Role[];
		country?: string;
		interests?: string;
	}

	const members: Member[] = [
		{
			name: "Polarity", 
			roles: ["Developer", "Problem Writer", "Testsolver"],
			country: "ca"

		},
		{
			name: "TheCelestialCube", 
			roles: ["Problem Writer", "Testsolver"],
			country: "ca"
		},
		{
			name: "AlwaysAJoke", 
			roles: ["Developer"],
			country: "ca"
		},
		{
			name: "Zephyr", 
			roles: ["Problem Writer", "Testsolver", "Outreach"],
			country: "us"
		},
		{
			name: "Void", 
			roles: ["Problem Writer", "Testsolver"],
			country: "in"
		},
		{
			name: "BariumLanthanum", 
			roles: ["Problem Writer", "Testsolver"],
			country: "ca"
		},
		{
			name: "Jeffrey Li", 
			roles: ["Problem Writer", "Testsolver"],
			country: "ca"
		},
	];
	
	members.forEach(member => {
		member.roles.sort();
	});
	/**
		members.sort((a, b) => {
			return a.name.localeCompare(b.name, 'en', { sensitivity: 'base' });
		});
	**/
</script>

<h1>MEA Team</h1>

<section class = "members">
	{#each members as member, i}
		<article class = "member" id = {'member-' + i}>
			<div class = "bar"></div>
			<div class = "member-identity"><h3>{member.name}</h3> <img class = "member-country" src={`https://flagcdn.com/${member.country}.svg`} alt={member.country} /></div>
			<p class = "member-roles">{member.roles.join(' • ')}</p>
		</article>
	{/each}
</section>

<style lang="scss">
	@import '../styles/colors';

	.members {
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
		flex-wrap: wrap;

		width: 100%;

		.member {
			min-width: 300px;
			
			padding: 20px;
			margin: 1em;

			box-shadow: 3px 0px 3px #eee, -3px 0px 3px #eee;

			transition: ease .3s;

			&:hover {
				transform: scale(1.02);
			}

			text-align: left;

			> .bar {
				width: 50px;

				border-top: 2px $blue-main solid;
			}

			.member-identity {
				display: inline-flex;
				align-items: center;

				.member-country {
					padding-left: 10px;
					height: 14px;
				}
			}

			.member-roles {
				color: #666;
				font-size: 14px;
				font-style: italic;
			}
		}
	}
</style>