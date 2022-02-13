<script lang="ts">
	import router from 'page';
	import Home from './components/Home.svelte';
	import About from './components/About.svelte';
	import Contests from './components/Contests.svelte';
	import Team from './components/Team.svelte';
	import NotFound from './components/404.svelte';
	import Navbar from './components/Navbar.svelte';
	import Footer from './components/Footer.svelte';
	import type { SvelteComponentDev } from "svelte/internal";
	
	let title: string;
	let page: typeof SvelteComponentDev;
	router ('/', () => [page, title] = [Home, 'Math et al.']);
	router ('/about', () => [page, title] = [About, 'About • MEA']);
	router ('/team', () => [page, title] = [Team, 'Team • MEA']);
	router ('/contests', () => [page, title] = [Contests, 'Contests • MEA']);
	router ('/vo', () => {
		window.location.href = 'https://virtual-olympiad.herokuapp.com';
	});
	router ('*', () => [page, title] = [NotFound, '404 • MEA']);

	router.start();
</script>

<svelte:head>
	<title>{title}</title>
	<link rel="preconnect" href="https://fonts.googleapis.com">
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
	<link href="https://fonts.googleapis.com/css2?family=Inter:wght@100;200;300;400;500;600;700;800&display=swap" rel="stylesheet"> 
</svelte:head>

<Navbar />
<main>
	<svelte:component this={page} />
	<Footer />
</main>

<style lang="scss" global>
	@import './styles/colors';

	h1 {
		color: $blue-main;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 400;
	}

	main {
		text-align: center;
		padding: 1em;	
		max-width: 240px;
		
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>