<script lang="ts">

</script>

<h1>CHESSKON</h1>

<article class = "contest-intro">
	<div class = "bar"></div>
	<h2>Math et Al + FISKON presents...</h2> 
	<p>
		CHESSKON is an international chess tournament hosted by Math et Al and FISKON. We have an open section and a U1200 section and great prizes for participants!
	</p>
	<p><a href="#Info">More Info >></a></p>

	<h3>To sign up...</h3>
	<p>Fill out the <a target = "_blank" href = "https://forms.gle/mSLgzZRGNoPL2ikS8">sign up form</a></p>
	<p>Join the <a target = "_blank" href = "https://www.chess.com/club/chesskon">chess.com club</a> for the matches!</p>
	<p>(Must complete both steps to participate)</p>
</article>
<article class = "contest-prizes">
	<div class = "bar"></div>
	<h2>Prizes</h2> 
	FISKON Premium to the top contestants.
	Virtual Olympiad Premium to the top contestants.
	More prizes to come!
</article>
<img class = "contest-poster" src="/CHESSKON.png" alt = "CHESSKON Poster"/>
<article class = "contest-info" id = "Info">
	<div class = "bar"></div>
	<h2>Info</h2> 
	<p>
		CHESSKON has an open section and a U1200 section (suggested rating). Anyone can choose to join either of the sections. However, if you are over 1200 elo rating we strongly suggest you join the open section for far better prizes and competitive matches.
	</p>
	<h3>Date</h3> 
	<p><em>Specific hours to be determined</em></p>
	<p>Open - Qualifying Arena @ April 3, Top 8 Knockout Bracket @ April 10</p>
	<p>U1200 - Arena @ April 3</p>
	<h3>Format</h3> 
	<p>Open - Qualifying Arena: 5+3. Top 8 from Arena move on to the finals with a Bracket Knockout: 10+3 format. Ties in Knockout are settled with an armageddon: White 5+0, Black 4+0 but White must win. Top finishers win prizes.</p>
	<p>U1200 - Arena: 5+3. Top finishers win prizes.</p>
	
	<h3>Sign up</h3> 
	<p>Fill out the <a target = "_blank" href = "https://forms.gle/mSLgzZRGNoPL2ikS8">sign up form</a></p>
	<p>Join the <a target = "_blank" href = "https://www.chess.com/club/chesskon">chess.com club</a> for the matches!</p>
	<p>(Must complete both steps to participate)</p>
</article>
<article class = "contest-sponsors">
	<div class = "bar"></div>
	<h2>Thanks to our sponsors!</h2> 
	<img height = "100px" title = "Not Copium" alt = "Copium" src = "https://gumlet.assettype.com/afkgaming%2F2021-08%2F79649079-d0e7-4acd-853b-6a2b92797da3%2Fcopium_png.png?format=auto"/>
</article>

<style lang="scss">
	@import '../../styles/colors';
	.contest-intro, .contest-prizes, .contest-info, .contest-sponsors {
		padding: 30px;
		width: clamp(300px, 40%, 1000px);
		text-align: left;
	}

	.contest-prizes, .contest-sponsors {
		display: flex;
		flex-direction: column;
		align-items: center;

		text-align: center;
	}

	.contest-poster {
		width: 100%;
		max-width: 500px;
	}

	.bar {
		width: 50px;

		border-top: 2px $blue-main solid;
	}

	@media (max-width: 500px) {
		.contest-intro, .contest-prizes, .contest-sponsors, .contest-info {
			padding: none;
		}
	}
</style>