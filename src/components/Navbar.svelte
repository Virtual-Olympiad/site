<nav>
    <div class = "nav-anchor-left">
        <a href = "/">Home</a>
        <a href = "/about">About</a>
        <a href = "/team">Team</a>
        <a href = "/contests">Contests</a>
        <a href = "/vo">VO</a>
    </div>
    <div class = "nav-anchor-right">
        <div>Portal</div>
    </div>
</nav>

<style lang="scss">
    nav {
		position: sticky;

		display: flex;
		align-items: center;
		justify-content: flex-start;

		top: 0;
		height: 30px;
		width: calc(100% - 2em);

		padding: 1em;

		background-color: #fff;

		.nav-anchor-left {
			margin-right: auto;
		}

		.nav-anchor-right {
			margin-left: auto;
		}

		> div {
			display: flex;

			div, a {
				padding: 0 10px;
			}
		}
	}
</style>