<script lang="ts">
	interface Question {
		title: string;
		content: string;
	}

	const questions: Question[] = [
		{
			title: "Is there a MEA Discord?",
			content: `You can join our active Discord server <a href="/discord">here</a> and participate in fun activities like POTW and The Linguistics Challenge as well as access many resources and an inclusive community.`
		}, 
		{
			title: "What upcoming projects are MEA planning?",
			content: "In a few months we are planning major updates to Virtual Olympiad with features including teams and Relay Mode."
		}, 
		{
			title: "When will Virtual Olympiad get an update?!",
			content: "Most of the development team (and mainly polarity) are busy with school and other things at the moment. In a few months we are planning major updates to Virtual Olympiad with features including teams and Relay Mode."
		}, 
		{
			title: "What are some events MEA is planning to organize in the future?",
			content: `We are looking forward to hosting contests in competitive math and competitive programming as well as events in strategic games like Chess and Tetris.`
		}, 
		{
			title: "What are some events MEA has organized?",
			content: `We have organized many events including CHESSKON, The Linguistics Challenge, MEA's POTW etc. More events are planned to come in the future. See the <a href="/contests#Past_Contests">Past Contests</a> section for more.`
		}, 
		{
			title: "Is MEA going to organize a contest?",
			content: `Yes, however we are short on problem writers and testsolvers so it will take some time before we are able to create a contest. If you would like to apply for those positions, please see <a href="/apply">here</a>.`
		},
		{
			title: "How qualified is the MEA team?",
			content: "Our team is highly qualified and includes several olympiad qualifiers from various fields of STEM including Math, Physics and CS."
		},
		{
			title: "Can I join the MEA team? How?",
			content: `See <a href="/apply">here</a> for application details and availability.`
		},
	];

	const questionToggles = (new Array(questions.length)).fill(false);
	
	const toggleQuestion = (index: number) => {
		questionToggles[index] = !questionToggles[index];
	}
</script>

<svelte:head>
    <meta name="description" content="All about Math et al!">
</svelte:head>

<h1>About & FAQ</h1>
<section class = "about">
	<article class = "about-founding">
		<h3>Math et Al</h3>
		<p>Math et al, also known as MEA, was founded in late 2021. Originally solely consisting of the Virtual Olympiad project, we evolved into a full STEM organization by early 2022.</p>
		<p>Our goal is to make competitive math (et al) more fun and enjoyable. We host many fun events in math, computer science, physics, chess, and more. If you're interested in joining our team or helping out for an event, apply <a href="/apply">here</a>!</p>
		<p>We have an active <a href="/discord" target="_blank">discord server</a> with fun events like Problem of the Week and The Linguistics Challenge.</p>
	</article>

	<article class = "about-projects">
		<h3>Virtual Olympiad</h3>
		<p>Virtual Olympiad (VO or VOLY) is an online multiplayer practice platform for the AMC and AIME (and more to come!). Host highly customizable practice contests using questions from past contests and compete against your friends. VO not only helps you prepare for the AMC/AIME, but also provides a fun and competitive spin to contest math.</p>
		<p><a href = "/vo">Visit >></a></p>
	</article>
</section>

<section class = "faq" id="FAQ">
	<div class = "bar"></div>
	<h1>FAQ</h1>
	{#each questions as question, i}
		<article class = "faq-question">
			<div class = "faq-info">
				<h3 class = "faq-title">{question.title}</h3>
				<div class = {"faq-toggle " + (questionToggles[i] ? "toggled":"")} on:click={()=> toggleQuestion(i)}>
					<span></span>
					<span></span>
				</div>
			</div>
			<p class = {"faq-content " + (questionToggles[i] ? "toggled":"")}>{@html question.content}</p>
		</article>
	{/each}
</section>

<style lang="scss">
	@import '../styles/colors';

	article {
		width: clamp(300px, 80%, 1000px);

		padding: 10px 30px;
		margin-bottom: 1em;

		border-left: 2px $blue-main solid;

		text-align: left;

		box-shadow: 3px 3px 3px #eee, -1px 1px 3px $blue-main;

		transition: ease .3s;

		&:hover {
			transform: scale(1.02);
		}
	}

	.about, .faq {
		display: flex;
		flex-direction: column;
		align-items: center;
		
		width: 100%; 

		margin-bottom: 1em;
	}

	.bar {
		width: 50px;

		border-top: 2px $blue-main solid;
	}

	.faq {
		h1 {
			background-color: transparent;
			color: $blue-main;

			padding: initial;
			margin: .5em;
		}

		.faq-info {
			display: flex;
			align-items: center;
		}

		.faq-title {
			margin-right: 1em;
		}

		.faq-content {
			display: none;

			&.toggled {
				display: block;
			}
		}

		.faq-toggle {
			position: relative;

			width: 2em;
			height: 2em;

			margin-left: auto;

			&:hover {
				cursor: pointer;
			}

			&.toggled {
				> span {
					&:nth-child(1) {
						transform: rotate(-45deg);
					}
					
					&:nth-child(2) {
						transform: rotate(45deg);
					}
				}
			}

			> span {
				position: absolute;
				display: block;

				width: 16px;
				height: 1px;

				background-color: #000;

				transform-origin: center;
				transition-duration: 75ms;
				transition-property: background-color, opacity, transform;
				transition-timing-function: ease-out;
				
				&:nth-child(1) {
					left: calc(50% - 13.3px);
					top: calc(50%);
					transform: rotate(45deg);
				}

				&:nth-child(2) {
					left: calc(50% - 2px);
					top: calc(50%);
					transform: rotate(-45deg);
				}
			}
		}
	}
</style>