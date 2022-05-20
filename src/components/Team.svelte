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
		description?: string;
	}

	const members: Member[] = [
		{
			name: "Polarity", 
			roles: ["Developer", "Events", "Problem Writer", "Resource Creator"],
			country: "ca",
			description: "Polarity is a top 20 national olympiad contestant who is interested in Math and CS: specifically web development, security, and algorithmics. He enjoys playing tetris, ping pong, and reading manga in his free time."
		},
		{
			name: "TheCelestialCube", 
			roles: ["Events", "Problem Writer", "Resource Creator"],
			country: "ca",
			description: "TheCelestialCube is a sophomore interested in math with achievements such as top 3 on the CTMC and top 20 on the CSMC. He enjoys listening to music, playing chess, and reading chinese light novels."
		},
		{
			name: "AlwaysAJoke", 
			roles: ["Developer"],
			country: "ca",
			description: "AlwaysAJoke is a competitive programmer who also enjoys math, NLP, and robotics. He has more than 800 volunteer hours and a black belt in karate. In his free time he plays badminton."
		},
		{
			name: "Void", 
			roles: ["Events", "Testsolver"],
			country: "in",
			description: "Void is a Science and Maths guy whose ears perk up whenever someone talks about anything related to linux, rubiks cube, movies, anime, and novels. He likes to write blogs and poetry in his free time and is a 2 time RMO qualifier."
		},
		{
			name: "Jeffrey Li", 
			roles: ["Problem Writer", "Resource Creator"],
			country: "ca",
			description: "Jeffrey is a Physics student with achievements from a variety of contests including CAP and CAYPT. He is also interested in Business, placing 5th in FBLA security investment and obtaining a silver award on ASDAN. He plays tennis in his free time."
		},
		{
			name: "BariumLanthanum", 
			roles: ["Problem Writer", "Testsolver", "Developer"],
			country: "ca",
			description: "BariumLanthanum is a CS enthusiast who enjoys developing software in his free time, mainly AI stuff. He is also very interested in math and physics. He enjoys listening to music, watching movies and anime, and playing videogames."
		{
			name: "Zephyr", 
			roles: ["Media", "Testsolver"],
			country: "us",
			description: "Zephyr is a middle schooler from the US. He is very involved in the STEM community and is a member of several organizations."
		},
		{
			name: ".A", 
			roles: ["Resource Creator", "Testsolver"],
			country: "ca",
			description: ".A is an Engineering enthusiast who has designed many models and small inventions. He likes to play realistic flight simulators and FPS games in his free time, and is a competitive swimmer."
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
			<p class = "member-description">{member.description ?? ""}</p>
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
			max-width: 400px;
			
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

			.member-description {
				margin-top: 2em;
			}
		}
	}
</style>
