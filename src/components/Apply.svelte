<script lang="ts">
	const roles = [
		{value: 'Developer', description: 'Contributes to our website and projects like Virtual Olympiad'},
		{value: 'Problem Writer', description: 'Comes up with original problems for resources and contests'},
		{value: 'Testsolver', description: 'Testsolves our problems and contests for quality assurance and feedback'},
		{value: 'Media', description: 'Contributes to our social presence and creates media (posters, videos, etc) for our events or contests'},
		{value: 'Events', description: 'Organizes and handles logistics for our events'},
		{value: 'Resource Creator', description: 'Creates original resources (handouts, videos, etc) as resources for our community'},
	];
</script>

<svelte:head>
    <meta name="description" content="Apply for the Math et al Team!">
</svelte:head>

<h1>Join Us!</h1>

<article class = "apply">
	<div class = "bar"></div>
	<h2>We are looking for passionate people to join our team!</h2>
	<p>Roles:</p>
	<ul>
		{#each roles as roles, i}
			<li>{roles.value} - {roles.description}</li>
		{/each}
	</ul> 
	<p>We are an easygoing and friendly team :). We respect your time and privacy, contribute when you would like to. Your information (such as from this form) will be shared with executives for essential purposes (like recruitment) only.</p>
	<p>Volunteer hours will be given out to members for their work soon.</p>
	<p>Fill out the form <a href="/applyform" target="_blank">here</a> to apply!</p>
</article>

<style lang="scss">
	@import '../../styles/colors';

	article {
		margin: 1em 0;
		padding: 30px;

		width: clamp(300px, 60%, 1000px);
		text-align: left;

		box-shadow: 3px 0px 3px #eee, -3px 0px 3px #eee;

		transition: ease .3s;

		&:hover {
			transform: scale(1.02);
		}
	}

	.bar {
		width: 50px;

		border-top: 2px $blue-main solid;
	}

	@media (max-width: 500px) {
		.apply {
			padding: none;
		}
	}
</style>