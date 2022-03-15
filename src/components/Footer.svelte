<script lang="ts">
</script>
<footer class="footer">
    <div class = "footer-info">
		<h3>Math et al</h3>
		<p class = "footer-copyright">© 2022-present Math et al</p>
		<div class = "footer-links">
			<a target = "_blank" href = "https://discord.gg/3eXC9UE6rT"><img alt = "discord" src = "https://cdnjs.cloudflare.com/ajax/libs/simple-icons/6.11.0/discord.svg"/></a>
			<a target = "_blank" href = "https://github.com/Math-et-al"><img alt = "github" src = "https://cdnjs.cloudflare.com/ajax/libs/simple-icons/6.11.0/github.svg"/></a>
			<a href = "#"><img alt = "twitter" src = "https://cdnjs.cloudflare.com/ajax/libs/simple-icons/6.11.0/twitter.svg"/></a>
			<a href = "#"><img alt = "instagram" src = "https://cdnjs.cloudflare.com/ajax/libs/simple-icons/6.11.0/instagram.svg"/></a>
		</div>
	</div>

	<div class = "footer-info">
		<h3>Information</h3>
		<p><a href = "/about">About</a></p>
		<p><a href = "/about#FAQ">FAQ</a></p>
		<p><a href = "/apply">Apply to MEA</a></p>
	</div>

	<div class = "footer-resources">
		<h3>Resources</h3>
		<p><a href = "/resources">Handouts</a></p>
		<p><a href = "/resources#POTW">POTW</a></p>
		<p><a href = "/vo">Virtual Olympiad</a></p>
	</div>

	<div class = "footer-events">
		<h3>Events</h3>
		<p><a href = "/contests/chesskon">CHESSKON</a></p>
		<p><a href = "/contests#Past_Contests">Past Contests</a></p>
	</div>
</footer>

<style lang="scss">
    @import "../styles/colors";
	
	.footer {
		display: flex;
		justify-content: space-evenly;
		align-items: stretch;
		flex-wrap: wrap;

		width: 100%;
		padding: 3em 2em 5em 2em;

		color: #eee;
		font-size: 14px;
		font-weight: 500;

		background: $blue-main;
		
		a {
			text-decoration: none;
			color: inherit;
		}

		h3 {
			color: #fff;
		}	
		
		> div {
			display: flex;
			flex-direction: column;

			margin: 0 20px;
			max-width: 200px;
		}

		.footer-links {
			display: flex;
			flex-direction: row;

			margin-top: 10px;

			img {
				filter: invert(1);
				height: 24px;
			}

			a + a {
				padding-left: 10px;
			}
		}

		/**
		.footer-copyright {
			color: #111;
		}
		**/
	}

	@media(max-width: 960px){
		.footer {
			flex-direction: column;
			align-items: center;
			text-align: center;

			> div {
				align-items: center;
			}
		}
	}
</style>
