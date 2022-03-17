<script lang="ts">
	type navTypes = 'home' | 'about' | 'team' | 'contests' | 'resources' | 'apply';

	let mobileNavToggle = false;

	const toggleMobileNav = () => {
		mobileNavToggle = !mobileNavToggle;
	}

	interface navButton {
		type?: navTypes;
		content: string;
		href: string;
		target?: string;
	}

	const navButtons: navButton[] = [
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
			type: 'resources',
			content: 'Resources',
			href: '/resources'
		},
		{	
			type: 'apply',
			content: 'Join MEA',
			href: '/apply'
		},
		{
			content: 'VO',
			href: '/vo',
			target: '_blank'
		},
	];

	export let page: string;
</script>

<nav>
    <div class = "nav-anchor-left">
		<a class = {"nav-logo " + (page && page == "home" ? "nav-current":"")} href="/">
			<img class = "logo" src = "/images/favicon.png" alt = "Math et al"/>
		</a>
		{#each navButtons as navButton, i}
			<a class = {page && page == navButton.type ? "nav-current":""} href = {navButton.href} target = {navButton.target ?? ""}>{navButton.content}</a>
		{/each}
    </div>
	<!--
    <div class = "nav-anchor-right">
        <div>Portal</div>
    </div>
	-->

	<div class = {"nav-burger " + (mobileNavToggle ? "active":"")} on:click={toggleMobileNav}>
        <span></span>
		<span></span>
		<span></span>
    </div>
</nav>

<div class =  {"mobile-nav " + (mobileNavToggle ? "active":"")}>
	{#each navButtons as navButton, i}
		<a class = {page && page == navButton.type ? "nav-current":""} href = {navButton.href} on:click={toggleMobileNav}>{navButton.content}</a>
	{/each}
</div>

<style lang="scss">
	@import '../styles/colors';

	.mobile-nav {
		position: fixed;
		display: none;
		flex-direction: column;
		
		z-index: 100;

		width: 100%;

		background-color: #fff;

		box-shadow: 0px 5px 5px rgba(0, 0, 0, 0.1);


		> a {
			display: block;
			width: 100%;
			padding: .75em 1em;

			color: #000;

			&:hover {
				background-color: #eee;
			}

			&.nav-current {
				border-left: 2px solid $blue-main;
			}
		}
	}

    nav {
		position: fixed;

		display: flex;
		align-items: center;
		justify-content: flex-start;

		top: 0;
		height: 3em;
		width: 100%;

		z-index: 100;
		
		background-color: #fff;
		color: #000;

		box-shadow: 0px 3px 3px rgba(0, 0, 0, 0.1);

		.nav-anchor-left {
			margin-right: auto;
		}
		
		.nav-logo {
			height: 100%;

			padding: 5px 10px;

			> .logo {
				height: 100%;
			}

			&.nav-current {
				background-color: inherit;
				border-top: 2px $blue-main solid;
			}
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

		> .nav-burger {
			position: relative;
			display: none;

			width: 3em;
			height: 100%;

			margin-left: auto;

			&:hover {
				background-color: #eee;
			}

			&.active {
				> span {
					&:nth-child(1) {
						transform: translateY(5px) rotate(45deg);
					}

					&:nth-child(2) {
						opacity: 0;
					}
					
					&:nth-child(3) {
						transform: translateY(-5px) rotate(-45deg);
					}
				}
			}

			> span {
				position: absolute;
				display: block;

				left: calc(50% - 8px);

				width: 16px;
				height: 1px;

				background-color: #000;

				transform-origin: center;
				transition-duration: 75ms;
				transition-property: background-color, opacity, transform;
				transition-timing-function: ease-out;
				
				&:nth-child(1) {
					top: calc(50% - 6px);
				}

				&:nth-child(2) {
					top: calc(50% - 1px);
				}
				
				&:nth-child(3) {
					top: calc(50% + 4px);
				}
			}
		}
	}

	@media(max-width: 720px){
        nav {
			.nav-anchor-left > *:not(.nav-logo) {
				display: none;
			}

			> .nav-burger {
				display: block;
			}
		} 

		.mobile-nav.active {
			display: block;
		}
	}
</style>