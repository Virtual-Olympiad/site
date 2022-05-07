<script lang="ts">

</script>

<svelte:head>
    <meta name="description" content="CHESSKON is an international chess tournament hosted by Math et Al and FISKON with $150+ worth of prizes. Particpants can choose to participate in either the Open or U1200 section.">
</svelte:head>

<h1>
	MEAAC 1
	<p>Math et al's first Anniversary Contest</p>
</h1>

<article class = "contest-intro">
	<div class = "bar"></div>
	<h2>It's been one year since the start of our organization!</h2> 
	<p>
		To celebrate, Math et al will be having a 1 week long event week with various events and prizes in our Discord server!
        <br/><br/>
        This includes our MEAAC 1, our first anniversary Math + Physics contest with high quality original problems by our staff.
        <br/><br/>
        Members can participate in teams up to two and we encourage each Math specialized member to find a Physics one to collaborate and vice versa.
	</p>
    <p><em>The question paper will be posted when MEAAC starts at 12am on May 12</em></p>
    <p><a href="#Info">Info >></a></p>
	<p><a href="#Prizes">Participants can also win prizes! >></a></p>

	<h3>To participate...</h3>
    <p>Both members must be in the active 100+ member Math et al <a target = "_blank" href = "/discord">Discord Server</a>!</p>
	<p>Team Leader can fill out the <a target = "_blank" href = "https://forms.gle/AQZ4xjrsKFyjFJoU9">submission form</a> with their solutions before the deadline</p>
</article>
<article class = "contest-info" id = "Info">
    <div class = "bar"></div>
	<h2>Info</h2> 
	<h3>Date</h3> 
	<p>MEAAC submissions will start on May 12 12am EST and end on May 19 12am EST</p>
	<h3>Format</h3> 
    <p>
        There will be 5 Math and 5 Physics questions, some with subquestions. The difficulty of both subjects range from Low AIME to Low-Medium Olympiad level. Participate in teams up to 2.
    </p>
	<p>Each question is proof by default, you must provide a full solution; a final answer by itself it worth nothing. However, you may provide solely the final answer to problems marked by an asterisk (*). Part marks may be given for incomplete progess, including on * problems, so submit what you have.</p>
    <p>The maximum possible amount of points awarded for each problem is given in the document. Your team's final score is the sum of the points attained over all problems. Problems are generally sorted in increasing order of difficulty.</p>
    <p>Both pictures of hand written solutions and LaTeX pdfs are accepted. Handwritten solutions should be clear and legible.</p>
	<p>All questions are original and made by our staff. Enjoy!</p>
	
	<h3>Rules</h3> 
	<ul>
        <li>Calculator allowed for basic arithmetic calculations only</li>
        <li>No resources allowed (internet, books, wolframalpha etc)</li>
        <li>No communication about the problems with anyone other than teammate(s)</li>
    </ul>
    <p>Both members must be in the active 100+ member Math et al <a target = "_blank" href = "/discord">Discord Server</a>!</p>
</article>
<article class = "contest-prizes" id="Prizes">
    <div class = "bar"></div>
    <h2>Prizes</h2> 
    <p>Each member in the winning team will recieve Discord Nitro Classic (teaming is encouraged)!</p>
    <p>Each member in the top 3 teams will recieve the event-exclusive lifetime Virtual Olympiad Pro License!</p>
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