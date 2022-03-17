<script lang="ts">

</script>

<svelte:head>
    <meta name="description" content="CHESSKON is an international chess tournament hosted by Math et Al and FISKON. We have an open section and a U1200 section and great prizes for participants!">
</svelte:head>

<h1>Join Us!</h1>

<article class = "apply">
	<div class = "bar"></div>
	<h2>Applications are currently closed as we figure out some details</h2> 
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