<script lang="ts">
	import { beforeUpdate, onMount } from 'svelte';
    import axios from 'axios';
    import HomeAnim from './HomeAnim.svelte';

	let width: number, height: number;

    type TargetType = 'site' | 'vo';
    type AnnouncementType = 'dev' | 'event';

    interface Announcement {
        message: string;
        url?: string;
        target: TargetType;
        type: AnnouncementType;
    }

    let announcements: Announcement[] = [];
    let announcementToggle = [];

    onMount(async ()=> {
        announcements = (await axios('https://mathetal.polarity.workers.dev/api/announcements/site')).data as Announcement[];
        announcementToggle = (new Array(announcements.length)).fill(true);
    });

    const toggleAnnouncement = (index: number) => {
        announcementToggle[index] = false;
    };
</script>

<svelte:head>
    <meta name="description" content="STEM organization aiming to help students learn and have fun">
</svelte:head>

{#each announcements as announcement, i}
    {#if announcementToggle[i]}
        <div class = {"announcement announcement-type-" + announcement.type}>
            <a href = {announcement.url}>
                {announcement.message}
            </a>
            <div class = "announcement-toggle" on:click|once = {()=> toggleAnnouncement(i)}>&#x2715</div>
        </div>
    {/if}
{/each}

<header>
	<div class = "header-background" bind:clientWidth={width} bind:clientHeight={height}>
		<HomeAnim width={width} height={height}/>
	</div>
    <div></div>
    <div class="header-title">
        <h1>Math et al.</h1>
        <p class="header-description">
            STEM organization aiming to help students learn and have fun
        </p>
    </div>

    <div class="header-social">
        <a target = "_blank" href = "/discord"><img alt = "discord" src = "https://cdnjs.cloudflare.com/ajax/libs/simple-icons/6.11.0/discord.svg"/></a>
        <a target = "_blank" href = "/github"><img alt = "github" src = "https://cdnjs.cloudflare.com/ajax/libs/simple-icons/6.11.0/github.svg"/></a>
        <a target = "_blank" href = "/twitter"><img alt = "twitter" src = "https://cdnjs.cloudflare.com/ajax/libs/simple-icons/6.11.0/twitter.svg"/></a>
        <a href = "/email"><img alt = "email" src = "https://cdnjs.cloudflare.com/ajax/libs/simple-icons/6.11.0/gmail.svg"/></a>
    </div>
</header>

<section class="cards">
    <article class="card">
        <h3>MEAAC 1</h3>
        <p>Math et al's first anniversary Math + Physics contest</p>
        <footer>
            <a href="/contests/meaac">Details >></a>
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

    h1 {
        background-color: transparent;
        color: $blue-main;

        padding: initial;
        margin: initial;
    }

    .announcement {
        width: 100%;
        padding: 1em;

        a, div {
            color: #fff;
        }

        &.announcement-type-dev {
            background-color: $green-main;
        }

        &.announcement-type-event {
            background-color: $blue-main;
        }

        .announcement-toggle {
            float: right;
            &:hover {
                cursor: pointer;
            }
        }
    }

    header {
        position: relative;
        display: flex;
        flex-flow: row nowrap;

        height: clamp(250px, 50vh, 500px);
        width: 100%;

        .header-description {
            padding: 0 10px;
            color: #666;
            font-style: italic;
        }

        .header-title {
            width: 100%;
            flex: none;
            margin-left: -100%;

            align-self: center;
        }

        .header-social {
            position: absolute;
            right: 0;
            bottom: .5em;
            flex: none;
            margin-right: 1em;

            padding: 10px 10px 5px 10px;

            background-color: #fff;
            border-radius: 10px;
            box-shadow: 3px 0px 3px rgba(0, 0, 0, 0.1), -3px 0px 3px rgba(0, 0, 0, 0.1);
            
            img {
				height: 24px;
                margin: 0 3px;

                transition: ease-out .3s;

                &:hover {
                    opacity: 80%;
                }
			}
        }

		.header-background {
			z-index: -1;

            flex: none;

			width: 100%;
			height: calc(100% + 20px);
		}
    }

    .cards {
        display: flex;
        align-items: center;
        justify-content: center;

        > .card {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: flex-start;

            height: 100%;
            min-height: 200px;

            width: clamp(300px, 30%, 600px);
            margin: 0 20px 20px 20px;
            padding: 10px;

			background: #fff;

            box-shadow: 0px 3px 3px #666;

            border-top: 2px $blue-main solid;

            transition: ease .3s;

			&:hover {
				transform: scale(1.02);
			}
        }
    }

	@media(max-width: 960px), (max-height: 640px){
        header {
            background-color: #eee;
            flex-direction: column;
            flex-wrap: initial;
            justify-content: space-between;
            align-items: center;

            .header-title {
                flex: initial;
                width: initial;
                margin-left: initial;
            }

            .header-background {
                display: none;
            }

            .header-social {
                position: relative;
                right: initial;
                bottom: initial;
                width: fit-content;
                margin: 1em;
            }
        }
	}

    @media(max-width: 960px){
        .cards {
            flex-direction: column;

            margin: 1em 0;
        }
	}
</style>
