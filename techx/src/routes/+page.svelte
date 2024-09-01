<script>
    import MediaQuery from "../MediaQuery.svelte";
    import gsap from "gsap";
    import ScrollTrigger from "gsap/dist/ScrollTrigger";
    import { onMount } from "svelte";
    import Lenis from "@studio-freight/lenis";
    import { navbarHeight } from "./store.js";
    import TextPlugin from "gsap/dist/TextPlugin";
    import Team from "./team.svelte";
    import { onDestroy } from "svelte";
    import Footer from "./footer.svelte";

    let windowHeight = 0;
    let windowWidth = 0;
    let photoIntroWidthHeight = 12;

    let pageX = 0;
    let pageY = 0;

    let scroll = 0;
    let svgShow = false;

    $: if (scroll > 800) {
        svgShow = true;
    }
    let lenis;

    const allImages = [
        "teamPhotos/teamPhoto.jpg",
        "teamPhotos/magazineOnTable.jpg",
        "teamPhotos/photoofmagazines.jpg",
    ];
    let ctx;

    onMount(() => {
        gsap.registerPlugin(ScrollTrigger, TextPlugin);
        ctx = gsap.context(() => {
            var intro = gsap
                .timeline({
                    defaults: {
                        transformOrigin: `${photoIntroWidthHeight / 2}rem -10rem`,
                        ease: "power1.inOut",
                        duration: 2,
                    },
                    scrollTrigger: {
                        trigger: ".intro",
                        start: "top 1%",
                        end: "+=100%",
                        scrub: true,
                        pin: true,
                        anticipatePin: 1,
                    },
                })
                .fromTo(
                    ".rev1",
                    { autoAlpha: 0 },
                    {
                        rotation: -360,
                        autoAlpha: 1,
                    },
                    "<0.05"
                )
                .fromTo(
                    ".rev2",
                    { autoAlpha: 0 },
                    {
                        rotation: -320,
                        autoAlpha: 1,
                    },
                    "<0.05"
                )
                .fromTo(
                    ".rev3",
                    { autoAlpha: 0 },
                    {
                        rotation: -280,
                        autoAlpha: 1,
                    },
                    "<0.05"
                )
                .fromTo(
                    ".rev4",
                    { autoAlpha: 0 },
                    {
                        rotation: -240,
                        autoAlpha: 1,
                    },
                    "<0.05"
                )
                .fromTo(
                    ".rev5",
                    { autoAlpha: 0 },
                    {
                        rotation: -200,
                        autoAlpha: 1,
                    },
                    "<0.05"
                )
                .fromTo(
                    ".rev6",
                    { autoAlpha: 0 },
                    {
                        rotation: -160,
                        autoAlpha: 1,
                    },
                    "<0.05"
                )
                .fromTo(
                    ".rev7",
                    { autoAlpha: 0 },
                    {
                        rotation: -120,
                        autoAlpha: 1,
                    },
                    "<0.05"
                )
                .fromTo(
                    ".rev8",
                    { autoAlpha: 0 },
                    {
                        rotation: -80,
                        autoAlpha: 1,
                    },
                    "<0.05"
                )
                .fromTo(
                    ".rev9",
                    { autoAlpha: 0 },
                    {
                        rotation: -40,
                        autoAlpha: 1,
                    },
                    "<0.05"
                );

            var page1 = gsap
                .timeline({
                    defaults: { duration: 3 },
                    scrollTrigger: {
                        trigger: ".pg1",
                        start: "top top",
                        end: "+=300%",
                        scrub: true,
                        pin: true,
                        anticipatePin: 1,
                    },
                })
                .from(".pg1Text1", { size: 0.95 })
                .fromTo(
                    ".slider",
                    {
                        yPercent: 120,
                        scale: 1.1,
                    },
                    {
                        yPercent: 0,
                        opacity: 1,
                        scale: 1.2,
                    }
                )
                .from(".pg1Text2", { yPercent: 120 }, "<1");

            var page3 = gsap
                .timeline({
                    defaults: { duration: 5 },
                    scrollTrigger: {
                        trigger: ".page3text",
                        start: "top center",
                        scrub: true,
                    },
                })
                .from(".page3text", { size: 0.95, opacity: 0 });
        });

        if (typeof window !== "undefined") {
            const lenis = new Lenis();
            lenis.on("scroll", (e) => {});
            function raf(time) {
                lenis.raf(time);
                requestAnimationFrame(raf);
            }
            requestAnimationFrame(raf);
        }
    });

    onDestroy(() => {
        ctx && ctx.revert();
    });
</script>

<svelte:window
    bind:outerHeight={windowHeight}
    bind:outerWidth={windowWidth}
    bind:scrollY={scroll}
    on:mousemove={(e) => ({ pageX, pageY } = e)}
/>
<div style="overflow: hidden; width: 100%;">
    <div
        class="page intro"
        style="height: calc(100vh - {$navbarHeight}px); padding: 0; margin: 0;"
    >
        <div
            style="z-index: 1; height: calc(100vh - {$navbarHeight}px); width: 100vw; position: absolute; display: flex; justify-content: center; align-items: center;"
        >
            <h1 style="text-align: center;">SAGE TECH-X MAGAZINE</h1>
        </div>

        <div
            class="revolvingStart"
            style="--revolvingPhotoWidth: {photoIntroWidthHeight}; z-index: 0;"
        >
            <img class="revolving rev1" src="1.1/p1.jpg" alt="example1" />
            <img class="revolving rev2" src="1.2/p1.jpg" alt="example2" />
            <img
                class="revolving rev3"
                src="3.2\finalTechX2023sem2-part-41024_1.jpg"
                alt="example3"
            />
            <img class="revolving rev4" src="2.1/p1.jpg" alt="example4" />
            <img class="revolving rev5" src="2.2/p2.jpg" alt="example5" />
            <img class="revolving rev6" src="1.3/p1.jpg" alt="example6" />
            <img class="revolving rev7" src="2.2/p1.jpg" alt="example7" />
            <img
                class="revolving rev8"
                src="3.2/finalTechX2023sem2-part-51024_1.jpg"
                alt="example8"
            />
            <img class="revolving rev9" src="1.2/p9.jpg" alt="example9" />
        </div>
    </div>

    <div style="height: 20rem;" />
    <div
        class="page pg1"
        style="height: calc(100vh - {$navbarHeight}px); border-radius: 0; z-index: 3;"
    >
        <MediaQuery query="(max-width: 800px)" let:matches>
            {#if matches}
                <h4
                    class="pg1Text1"
                    style="position: absolute; top: 2rem; right: 2rem; width: calc(100% - 4rem);"
                >
                    The Sage Tech-X Magazine hopes to inform and engage the Sage
                    Hill students and community about the state of STEM, its
                    transformative effects on society, and its limitless
                    possibilities in the future.
                </h4>
            {/if}
        </MediaQuery>
        <MediaQuery query="(min-width: 800px)" let:matches>
            {#if matches}
                <h3
                    class="pg1Text1"
                    style="position: absolute; top: 2rem; right: 2rem; width: calc(100% - 4rem);"
                >
                    The Sage Tech-X Magazine hopes to inform and engage the Sage
                    Hill students and community about the state of STEM, its
                    transformative effects on society, and its limitless
                    possibilities in the future.
                </h3>
            {/if}
        </MediaQuery>
        <div
            class="slider"
            style="background-color: antiquewhite; height: calc(100vh); position: absolute; width: 100%;"
        />
        <div class="pg1Text2" style="position: absolute;">
            <MediaQuery query="(min-width: 800px)" let:matches>
                {#if matches}
                    <div
                        style="width: 100vw; top: {$navbarHeight}px; bottom: 0; left: 0; height: calc(100vh - {$navbarHeight}px); display: grid; grid-template-columns: 1fr 1fr;"
                    >
                        <div
                            style="right: 0; background: linear-gradient(antiquewhite, rgba(250, 235, 215, 0) 20%, rgba(250, 235, 215, 0) 70%, antiquewhite 90%); position: absolute; width: 50%; z-index: 5; height: calc(100vh - {$navbarHeight}px); top: 0;"
                        />
                        <div style="margin-left: 2rem;">
                            <h1
                                style="color: var(--black); margin-bottom: 4rem;"
                            >
                                Our Story
                            </h1>
                            <p style="color: var(--black); max-width: 35rem;">
                                Started in 2021, Minki Shin (class of 2022)
                                created the Tech-X Magazine with the intention
                                to inspire an open and passionate STEM
                                community. The magazine gives students the
                                opportunity to share their interests and learn
                                from others. Learning how to distill complex
                                ideas into more digestable language is an
                                important skill, yet it's also an
                                under-practiced skill among many young STEM
                                students.
                            </p>
                            <p style="color: var(--black); max-width: 35rem;">
                                If you're interested in contributing to the
                                magazine, please contact our current
                                editor-in-chief Kevin Peng:
                                25pengk@sagehillschool.org.
                            </p>
                        </div>

                        <div
                            class="carousel-container"
                            style="height: calc(100vh - {$navbarHeight}px - 10px); margin-top: 5px; "
                        >
                            <div class="carousel-inner" style="z-index: -1;">
                                {#each [...allImages, ...allImages] as image, index (index)}
                                    <img
                                        src={image}
                                        alt={`${index}`}
                                        class="carousel-item"
                                    />
                                {/each}
                            </div>
                        </div>
                    </div>
                {/if}
            </MediaQuery>

            <MediaQuery query="(max-width: 800px)" let:matches>
                {#if matches}
                    <div
                        style="margin: 0; width: 100%; top: {$navbarHeight}px; bottom: 0; left: 0; height: calc(100vh - {$navbarHeight}px); display: flex; flex-direction: column; gap: 2rem; justify-content: center;"
                    >
                        <div
                            style="right: 0; background: linear-gradient(horizontal, antiquewhite, rgba(250, 235, 215, 0) 20%, rgba(250, 235, 215, 0) 50%, antiquewhite 80%); position: absolute; width: 100%; z-index: 5; height: 30rem; bottom: 0;"
                        />
                        <div style="margin-left: 2rem; margin-bottom: 0;">
                            <h1
                                style="color: var(--black); margin-bottom: 4rem; margin: 0;"
                            >
                                Our Story
                            </h1>
                            <p
                                style="color: var(--black); width: calc(100% - 4rem);"
                            >
                                Started in 2021, Minki Shin (class of 2022)
                                created the Tech-X Magazine with the intention
                                to inspire an open and passionate STEM
                                community. The magazine gives students the
                                opportunity to share their interests and learn
                                from others. Learning how to distill complex
                                ideas into more digestable language is an
                                important skill, yet it's also an
                                under-practiced skill among many young STEM
                                students.
                            </p>
                            <p
                                style="color: var(--black); width: calc(100% - 4rem);"
                            >
                                If you're interested in contributing to the
                                magazine, please contact our current
                                editor-in-chief Kevin Peng:
                                25pengk@sagehillschool.org.
                            </p>
                        </div>
                        <div
                            class="carousel-container"
                            style="margin-top: 1px;"
                        >
                            <div class="carousel-inner" style="z-index: -1;">
                                {#each [...allImages, ...allImages] as image, index (index)}
                                    <img
                                        src={image}
                                        alt={`${index}`}
                                        class="carousel-item"
                                    />
                                {/each}
                            </div>
                        </div>
                    </div>
                {/if}
            </MediaQuery>
        </div>
    </div>
</div>

<div style="height: 15rem;" />
<div class="page">
    <h1 class="page3text" style="margin: auto; text-align: center;">
        Meet Our Current Team
    </h1>
    <div style="height: 10rem;"></div>
    <Team />
</div>
<Footer />

<style>
    @media (max-width: 800px) {
        @keyframes scroll {
            0% {
                transform: translateX(0%);
            }
            100% {
                transform: translateX(-50%);
            }
        }
        .carousel-container {
            overflow: hidden;
            white-space: nowrap;
            width: calc(100vw - 4rem);
        }

        .carousel-item {
            flex: 0 0 auto;
            width: 25rem;
            height: auto;
            object-fit: cover;
            border-radius: 1rem;
        }
        .carousel-inner {
            animation: scroll 20s linear infinite; /* Adjust time as needed */
            display: flex;
            flex-direction: row;
            gap: 2rem;
        }
    }

    @media (min-width: 800px) {
        @keyframes scroll {
            0% {
                transform: translateY(0%);
            }
            100% {
                transform: translateY(-50%);
            }
        }
        .carousel-container {
            overflow: hidden;
            white-space: nowrap;
            margin: auto;
        }

        .carousel-item {
            flex: 0 0 auto;
            width: 20rem;
            height: auto;
            object-fit: cover;
            border-radius: 1rem;
        }
        .carousel-inner {
            animation: scroll 20s linear infinite; /* Adjust time as needed */
            display: flex;
            flex-direction: column;
            gap: 2rem;
        }
    }

    .revolving {
        width: calc(var(--revolvingPhotoWidth) * 1rem);
        height: auto;
        position: absolute;
        left: calc(50% - calc(var(--revolvingPhotoWidth) * 1rem) / 2);
        top: calc(50% + 5rem);
        visibility: hidden;
    }

    .page {
        padding: 2rem;
        margin: 0;
        z-index: 0;
        position: relative;
        border-radius: 2rem;
        overflow: hidden;
        width: 100%;
        box-sizing: border-box;
        margin-bottom: 10rem;
    }
</style>
