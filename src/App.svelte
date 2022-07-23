<script lang="ts">
	import router from 'page';

	// 
	import Home from './components/Home.svelte';
	import About from './components/About.svelte';
	import Team from './components/Team.svelte';
	import Apply from './components/Apply.svelte';

	// partials
	import Navbar from './components/Navbar.svelte';
	import Footer from './components/Footer.svelte';

	// 404
	import NotFound from './components/404.svelte';

	// contests
	import Contests from './components/Contests.svelte';
	import Chesskon from './components/contests/Chesskon.svelte';
	import MEAAC from './components/contests/MEAAC.svelte';

	// resources 
	import Resources from './components/Resources.svelte';
	import POTW from './components/resources/POTW.svelte';

	// ts
	import type { SvelteComponentDev } from "svelte/internal";
	
	let title: string;
	let page: typeof SvelteComponentDev;

	type navTypes = 'home' | 'about' | 'team' | 'contests' | 'resources' | 'apply';
	let navPage: navTypes;
	
	router ('/', () => [page, title, navPage] = [Home, 'Math et al.', 'home']);
	router ('/about', () => [page, title, navPage] = [About, 'About • MEA', 'about']);
	router ('/team', () => [page, title, navPage] = [Team, 'Team • MEA', 'team']);
	router ('/contests/:contest', (ctx) => {
		let { contest } = ctx.params;
		navPage = 'contests';

		switch (contest) {
			case 'chesskon':
				[page, title] = [Chesskon, 'CHESSKON • MEA']
			break;
			case 'meaac':
				[page, title] = [MEAAC, 'MEAAC • MEA']
			break;
			default:
				[page, title, navPage] = [NotFound, '404 • MEA', null] 
		}
	});
	router ('/contests', () => [page, title, navPage] = [Contests, 'Contests • MEA', 'contests']);
	router ('/resources/:resource', (ctx) => {
		let { resource } = ctx.params;
		navPage = 'resources';

		switch (resource) {
			case 'potw':
				[page, title] = [POTW, 'CHESSKON • MEA']
			break;
			default:
				[page, title, navPage] = [NotFound, '404 • MEA', null] 
		}
	});
	router ('/resources', () => [page, title, navPage] = [Resources, 'Resources • MEA', 'resources']);
	router ('/apply', () => [page, title, navPage] = [Apply, 'Apply • MEA', 'apply']);
	router ('/vo', () => {
		title = 'Virtual Olympiad • MEA';
		window.location.href = 'https://virtual-olympiad.herokuapp.com';
	});
	router ('/email', () => {
		title = 'Mail • MEA';
		window.location.href = 'mailto:contact@mathetal.org';
	});
	router ('/github', () => {
		title = 'Mail • MEA';
		window.location.href = 'https://github.com/Math-et-al';
	});
	router ('/discord', () => {
		title = 'Discord • MEA';
		window.location.href = 'https://discord.gg/3eXC9UE6rT';
	});
	router ('/twitter', () => {
		title = 'Twitter • MEA';
		window.location.href = 'https://twitter.com/math_et_al';
	});
	router ('/applyform', () => {
		title = 'Application Form • MEA';
		window.location.href = 'https://forms.gle/V2vAiX22XuTrUnz79';
	});
	
	router ('*', () => [page, title] = [NotFound, '404 • MEA']);

	router.start();
</script>

<svelte:head>
	<title>{title}</title>
	<link rel="preconnect" href="https://fonts.googleapis.com">
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
	<link href="https://fonts.googleapis.com/css2?family=Inter:wght@100;200;300;400;500;600;700;800&display=swap" rel="stylesheet"> 
	<meta name="theme-color" content="#0160e2">
	<meta name="keywords" content="math et al, mea, chesskon">
	<meta name="author" content="MEA Team">

	<meta property="og:site_name" content="Math et al">
	<meta property="og:url" content="mathetal.org">
	<meta property="og:image" content="/images/favicon.png">
	<meta property="og:type" content="website">
</svelte:head>

<Navbar page = {navPage}/>
<main>
	<svelte:component this={page} />
</main>
<Footer />

<style lang="scss" global>
	@import './styles/colors';

	h1 {
		width: 100%;

		margin: 0;
		margin-bottom: 1em;
		padding: 1em 0;
		
		background-color: $blue-main;

		color: #fff;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 400;

		> p {
			text-transform: initial;
			font-size: initial;
			font-weight: initial;
		}
	}

	main {
		text-align: center;
		margin-top: 3em;

		display: flex;
		flex-direction: column;
		align-items: center;

		min-height: calc(100vh - 1em);
	}
</style>