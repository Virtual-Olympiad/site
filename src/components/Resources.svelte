<script lang="ts">
	const CAPSolutions = [2014, 2015, 2016, 2017, 2018, 2019].sort((a, b)=> b - a);
</script>

<svelte:head>
    <meta name="description" content="Math et al's high quality resources, including the Virtual Olympiad multiplayer contest platform and high quality CAP Solutions.">
</svelte:head>

<h1>Resources</h1>

<section class = "resources">
    <article>
		<div class = "bar"></div>
		<h2>
			Virtual Olympiad
		</h2>
        <p>
            Virtual Olympiad (VO or VOLY) is a platform for hosting multiplayer practice math contests in a competitive style using questions from past contests!
        </p>
        <p>
            Built by polarity, VO allows students to create rooms and invite friends to do highly customizable mocks using previous AMC and AIME (more sources to come) questions! You and your friends can compete or practice and see who solves more questions in a time frame of your choice! VO not only helps you prepare for math contests, but also provides a fun and competitive spin to contest math.
        </p>
        <a href="/vo" target="_blank">Visit VO >></a>
        <a href="https://github.com/polarr/virtual-olympiad/wiki/Guide" target="_blank">VO user guide >></a>

        <p>More exciting modes and features such as Relay or Team vs Team are planned to come soon, so stay tuned!</p>
	</article>

	<article>
		<div class = "bar"></div>
		<h2>CAP Solutions</h2> 
		<p>
			Official solutions to questions from the Canadian Association of Physicists (CAP) High School Exam are usually nonexistant, or lackluster in quality in the rare occsasion that they exist.
        </p>
        <p>To help physics students get access to CAP help, Jeffrey Li from Math et Al has put together high quality step by step solutions to the CAP exam for the past several years.</p>
        {#each CAPSolutions as year, i}
            <a href={`/files/` + year + `CAP_answers.pdf`} download>{year} CAP Solutions</a>
        {/each}
	</article>

    <article>
		<div class = "bar"></div>
		<h2>Problem of the Week</h2> 
		<p>
			Every week we post an (usually original) interesting problem for each of Math, Physics, and CS. 
            The difficulty cycles every 4 weeks (with concrete math difficulty references in brackets): 
        </p>
        <ul>
            <li>Week 1: Hard (Mid AIME)</li>
            <li>Week 2: Difficult (High AIME)</li>
            <li>Week 3: Very Difficult (USAJMO)</li>
            <li>Week 4: Extremely Difficult (USAMO)</li>
        </ul>
        
        <p>Often the problems will be original, made up by our very qualified problem writers. Join the <a target = "_blank" href = "https://discord.gg/3eXC9UE6rT">discord server</a> to participate!</p>
	</article>
</section>

<style lang="scss">
	@import '../../styles/colors';

    li {
        text-align: left;
    }

	.resources {
		display: flex;
		flex-wrap: wrap;
		justify-content: center;

		width: 100%;

		padding: 1em;
        margin-bottom: 3em;

        > article, > section {
            display: flex;
            flex-direction: column;
            align-items: center;

            width: clamp(460px, 40%, 1000px);

            margin: 1em;
            padding: 30px;

            box-shadow: 3px 0px 3px #eee, -3px 0px 3px #eee;

            transition: ease .3s;

            &:hover {
                transform: scale(1.02);
            }
        }
	}
	.bar {
		width: 50px;

		border-top: 2px $blue-main solid;
	}

	@media (max-width: 1024px) {
		.resources {
			width: clamp(300px, 80%, 1000px);
		}
	}
</style>