<script lang="ts">
	type navTypes = 'home' | 'about' | 'team' | 'contests';

	interface navButton {
		type?: navTypes;
		content: string;
		href: string;
	}

	const navButtons: navButton[] = [
		{
			type: 'home',
			content: 'Home',
			href: '/'
		},
		{
			type: 'about',
			content: 'About',
			href: '/about'
		},
		{
			type: 'team',
			content: 'Team',
			href: '/team'
		},
		{
			type: 'contests',
			content: 'Contests',
			href: '/contests'
		},
		{
			content: 'VO',
			href: '/vo'
		},
	];

	export let page: string;
</script>

<nav>
    <div class = "nav-anchor-left">
		{#each navButtons as navButton, i}
			<a class = {page && page == navButton.type ? "nav-current":""} href = {navButton.href}>{navButton.content}</a>
		{/each}
    </div>
	<!--
    <div class = "nav-anchor-right">
        <div>Portal</div>
    </div>
	-->
</nav>

<style lang="scss">
	@import '../styles/colors';

    nav {
		position: fixed;

		display: flex;
		align-items: center;
		justify-content: flex-start;

		top: 0;
		height: 3em;
		width: 100%;

		padding: 0 1em;

		z-index: 100;
		
		background-color: #fff;
		color: #000;

		.nav-anchor-left {
			margin-right: auto;
		}

		.nav-anchor-right {
			margin-left: auto;
		}

		> div {
			display: flex;
			align-items: center;

			height: 100%;

			div, a {
				height: 100%;
				padding: 0 10px;
				color: #000;

				display: flex;
				align-items: center;

				border-top: 2px transparent solid;

				&:hover {
					background-color: #eee;
				}

				&.nav-current {
					background-color: #eee;
					border-top: 2px $blue-main solid;
				}
			}
		}
	}
</style>