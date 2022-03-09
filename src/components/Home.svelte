<script lang="ts">
	import { onMount } from 'svelte';

    import HomeAnim from './HomeAnim.svelte';

	let width: number, height:number;
</script>

<header>
	<div class = "header-background" bind:clientWidth={width} bind:clientHeight={height}>
		<HomeAnim width={width} height={height}/>
	</div>
    <div class="header-title">
        <h1>Math et al.</h1>
        <p class="header-description">
            STEM organization aiming to help students learn and have fun
        </p>
    </div>
</header>

<section class="cards">
    <article class="card">
        <h3>CHESSKON</h3>
        <p>Chess tourney with awesome prizes and 100+ projected participants</p>
        <footer>
            <a href="/chesskon">Details >></a>
        </footer>
    </article>
    <article class="card">
        <h3>Virtual Olympiad</h3>
        <p>Platform for hosting competitive multiplayer mock contests</p>
        <footer>
            <a href="/vo">Visit >></a>
        </footer>
    </article>
</section>

<style lang="scss">
    @import "../styles/colors";

    header {
        display: flex;
        align-items: center;
        justify-content: center;

        height: clamp(250px, 50vh, 500px);
        width: 100%;

        .header-description {
            color: #666;
            font-style: italic;
        }

		.header-background {
			position: absolute;
			top: 2em;
			left: 0;

			z-index: -1;

			width: 100%;
			height: 50%;
		}
    }

    .cards {
        display: flex;
        align-items: center;
        justify-content: center;

        height: 200px;

        > .card {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: flex-start;

            height: 100%;
            width: clamp(300px, 30%, 600px);
            margin: 20px;
            padding: 10px;

			background: #fff;

            box-shadow: 0px 3px 3px #666;

            border-top: 2px $blue-main solid;
        }
    }

	@media(max-width: 960px), (max-height: 640px){
		.header-background {
			display: none;
		}
	}
</style>
