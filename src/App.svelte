<script lang="ts">
	import router from 'page';
	import Home from './components/Home.svelte';
	import About from './components/About.svelte';
	import Contests from './components/Contests.svelte';
	import Team from './components/Team.svelte';
	import type { SvelteComponentDev } from "svelte/internal";
	
	let title: string;
	let page: typeof SvelteComponentDev;
	router ('/', () => [page, title] = [Home, 'Virtual Olympiad']);
	router ('/about', () => [page, title] = [About, 'About • VO']);
	router ('/team', () => [page, title] = [Team, 'Team • VO']);
	router ('/contests', () => [page, title] = [Contests, 'Contests • VO']);
	router ('/VOMP', () => {
		window.location.href = 'https://virtual-olympiad.herokuapp.com';
	});

	router.start();
</script>

<svelte:head>
	<title>{title}</title>
</svelte:head>
<svelte:component this={page} />