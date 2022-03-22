<script lang="ts">

</script>

<svelte:head>
    <meta name="description" content="CHESSKON is an international chess tournament hosted by Math et Al and FISKON. We have an open section and a U1200 section and great prizes for participants!">
</svelte:head>

<h1>CHESSKON</h1>

<article class = "contest-intro">
	<div class = "bar"></div>
	<h2>Math et Al + FISKON presents...</h2> 
	<p>
		CHESSKON is a free to join international chess tournament hosted by Math et Al and FISKON. We have an open section and a U1200 section and great prizes for participants!
	</p>
	<p>
		Thanks to <a href="https://artofproblemsolving.com">Art of Problem Solving</a> for sponsoring us!
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
	<p>Thanks to our <a href="#Sponsors">sponsors!</a></p>
	<h3>Open section</h3>
	<ul>
		<li>Art of Problem Solving <em>$25 Coupons</em> to the top 3 finishers</li>
		<li>Virtual Olympiad <em>Cookie version</em> to the top 3 finishers (will become valid in some time)</li>
		<li>FISKON <em>Premium</em> for a month to all participants</li>
	</ul>		
	<h3>U1200 section</h3>
	<ul>
		<li>$25 Art of Problem Solving Coupon to the winner</li>
		<li>FISKON <em>Premium</em> for a month to all participants</li>
	</ul>
</article>
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
<article class = "contest-sponsors" id="Sponsors">
	<div class = "bar"></div>
	<h2>Thanks to our sponsors!</h2> 
	<img alt = "Art of Problem Solving" src = "/images/CHESSKON_AoPS_Main_Logo.png"/>
</article>

<style lang="scss">
	@import '../../styles/colors';

	article {
		margin: 1em 0;
		padding: 30px;

		width: clamp(300px, 60%, 1000px);
		text-align: left;

		box-shadow: 3px 0px 3px #eee, -3px 0px 3px #eee;

		transition: ease .3s;

		&:hover {
			transform: scale(1.02);
		}
	}

	.contest-prizes, .contest-sponsors {
		display: flex;
		flex-direction: column;
		align-items: center;

		text-align: center;
	}
	
	.contest-sponsors img {
		width: 100%;
		max-height: max-content;

		box-shadow: 2px 0px 2px #eee, -2px 0px 2px #eee;
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