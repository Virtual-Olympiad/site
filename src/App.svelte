<script lang="ts">
	export let name: string;
</script>

<main>
	<h1>Virtual Olympiad</h1>
	<p>STEM Olympiad Organization aiming to help students learn and have fun</p>

	<div>
		Trainer
	</div>
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

	div { 
		
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>