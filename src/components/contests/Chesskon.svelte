<script lang="ts">

</script>

<svelte:head>
    <meta name="description" content="CHESSKON is an international chess tournament hosted by Math et Al and FISKON with $150+ worth of prizes. Particpants can choose to participate in either the Open or U1200 section.">
</svelte:head>

<h1>
	CHESSKON
	<p>Sponsored by Art of Problem Solving</p>
</h1>

<article class = "contest-intro">
	<div class = "bar"></div>
	<h2>Math et Al + FISKON presents...</h2> 
	<p>
		CHESSKON is a free to join international chess tournament hosted by Math et Al and FISKON with $150+ worth of prizes. Particpants can choose to participate in either the Open or U1200 section.
	</p>
	<p><a href="#Prizes">See Prizes >></a></p>
	<p><a href="#Info">Jump to Info >></a></p>
	<p><a href="#Sponsors">Thanks to our sponsors!</a></p>

	<h3>To sign up...</h3>
	<p>Fill out the <a target = "_blank" href = "https://forms.gle/mSLgzZRGNoPL2ikS8">sign up form</a></p>
	<p>Join the <a target = "_blank" href = "https://www.chess.com/club/chesskon">chess.com club</a> for the matches!</p>
	<p>(Must complete both steps to participate)</p>
</article>
<article class = "contest-prizes" id="Prizes">
	<div class = "bar"></div>
	<h2>Prizes</h2> 
	<p>Prizes are made available thanks to our <a href="#Sponsors">sponsors</a>.</p>
	<h3>Open section</h3>
	<ul>
		<li>$25 Art of Problem Solving Coupons to the top 3 finishers</li>
		<li>FISKON Premium for a month to all participants</li>
	</ul>		
	<h3>U1200 section</h3>
	<ul>
		<li>$25 Art of Problem Solving Coupon to the winner</li>
		<li>FISKON Premium for a month to all participants</li>
	</ul>
</article>
<article class = "contest-info" id = "Info">
	<div class = "bar"></div>
	<h2>Info</h2> 
	<p>
		CHESSKON has an Open section and a U1200 section (suggested rating). Anyone can choose to join the Open section (although if you are under 1200 elo it is suggested you join U1200). However, if you are over 1200 elo rating you must join the Open section for superior prizes and competitive matches.
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
	<p>If you would like to sponsor us, contact us at contact@mathetal.org</p>
	<a href="https://artofproblemsolving.com" target="_blank"><img alt = "Art of Problem Solving" src = "/images/CHESSKON_AoPS_Main_Logo.png"/></a>
	<p><a href="/files/CHESSKON_AoPS_FlyersForSponsorships.pdf">Learn more about AoPS >></a></p>
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
		padding: 1em;

		border-radius: 10px;

		box-shadow: 2px 0px 1px #eee, -2px 0px 1px #eee;
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