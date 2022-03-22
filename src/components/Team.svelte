<script lang="ts">
	import Select from 'svelte-select';

	type Role = 'Developer' | 'Problem Writer' | 'Testsolver' | 'Media' | 'Events' | 'Resource Creator';

	const RoleTypes = [
		{value: 'Developer', label: 'Developer'},
		{value: 'Problem Writer', label: 'Problem Writer'},
		{value: 'Testsolver', label: 'Testsolver'},
		{value: 'Media', label: 'Media'},
		{value: 'Events', label: 'Events'},
		{value: 'Resource Creator', label: 'Resource Creator'},
	];

	interface Member {
		name: string;
		roles: Role[];
		country?: string;
		interests?: string;
	}

	const members: Member[] = [
		{
			name: "Polarity", 
			roles: ["Developer", "Events", "Problem Writer", "Resource Creator"],
			country: "ca"

		},
		{
			name: "TheCelestialCube", 
			roles: ["Events", "Problem Writer", "Resource Creator"],
			country: "ca"
		},
		{
			name: "AlwaysAJoke", 
			roles: ["Developer"],
			country: "ca"
		},
		{
			name: "Void", 
			roles: ["Events", "Testsolver"],
			country: "in"
		},
		{
			name: "Jeffrey Li", 
			roles: ["Problem Writer"],
			country: "ca"
		},
		{
			name: "BariumLanthanum", 
			roles: ["Problem Writer"],
			country: "ca"
		},
		{
			name: "Zephyr", 
			roles: ["Media", "Testsolver"],
			country: "us"
		},
		{
			name: ".A", 
			roles: ["Resource Creator", "Testsolver"],
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
	
	let filteredMembers = members;
	let filter: string = 'All';

	const filterRoles = (e, clear = false) => {
		filter = e.detail?.value;
		if (filter == 'All' || clear){
			filter = 'All';
			filteredMembers = members;
			return;
		}

		filteredMembers = members.filter(member => {
			return member.roles.includes(filter as Role);
		});
	}
</script>

<svelte:head>
    <meta name="description" content="The amazing Math et al team!">
</svelte:head>

<h1>MEA Team</h1>

<Select placeholder={'Filter By...'} containerStyles={`width: 200px;`} items={RoleTypes} on:select={filterRoles} on:clear={(e)=> filterRoles(e, true)}></Select>
<section class = "members">
	{#each filteredMembers as member, i}
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

		margin-bottom: 3em;

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