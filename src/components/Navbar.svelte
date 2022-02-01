<nav>
    <div class = "header-anchor-left">
        <a href = "/">Home</a>
        <a href = "/about">About</a>
        <a href = "/team">Team</a>
        <a href = "/contests">Contests</a>
        <a href = "/VOMP?redirect=true">VOMP</a>
    </div>
    <div class = "header-anchor-right">
        <div>Portal</div>
    </div>
</nav>

<style lang="scss">
    nav {
		display: flex;
		align-items: center;
		justify-content: flex-start;

		width: 100%;

		.header-anchor-left {
			margin-right: auto;
		}

		.header-anchor-right {
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