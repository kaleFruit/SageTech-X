<script>
    let windowHeight = 0;
    import MediaQuery from "../../MediaQuery.svelte";
    import Edition41 from "./archive4.1.svelte";
    import Edition32 from "./archive3.2.svelte";
    import Edition31 from "./archive3.1.svelte";
    import Edition22 from "./archive2.2.svelte";
    import Edition21 from "./archive2.1.svelte";
    import Edition13 from "./archive1.3.svelte";
    import Edition12 from "./archive1.2.svelte";
    import Edition11 from "./archive1.1.svelte";
    import PreviousTeamMembers from "./previousMembers.svelte";
    import Footer from "../footer.svelte";

    import gsap from "gsap";
    import ScrollTrigger from "gsap/dist/ScrollTrigger";
    import { onMount } from "svelte";
    import Lenis from "@studio-freight/lenis";
    import { navbarHeight } from "../store.js";
    import { onDestroy } from "svelte";

    let totalNumEditions = 8;

    onMount(() => {
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
</script>

<svelte:window bind:outerHeight={windowHeight} />

<div class="intro">
    <h1
        style="
      padding-top: 8rem;
      text-align: center;
      padding-bottom: 8rem;
      margin: auto;
      "
    >
        ARCHIVES
    </h1>
    <div class="announcement-container">
        <div class="announcement-inner">
            <span>Edition 4.1 is Now Out!</span>
            <span>Edition 4.1 is Now Out!</span>
            <span>Edition 4.1 is Now Out!</span>
            <span>Edition 4.1 is Now Out!</span>
            <span>Edition 4.1 is Now Out!</span>
            <span>Edition 4.1 is Now Out!</span>
        </div>
    </div>
</div>
<div style="height: 1rem;" />
<div class="container">
    <div class="backgroundDiv" />
    <div class="edition">
        <Edition41 />
    </div>
    <div class="edition">
        <Edition32 />
    </div>

    <div class="edition">
        <Edition31 />
    </div>

    <div class="edition">
        <Edition22 />
    </div>

    <div class="edition">
        <Edition21 />
    </div>

    <div class="edition">
        <Edition13 />
    </div>

    <div class="edition">
        <Edition12 />
    </div>

    <div class="edition">
        <Edition11 />
    </div>
</div>
<PreviousTeamMembers />
<Footer />

<style>
    .container {
        width: 100%;
        height: 100%;
        justify-content: center;
        align-items: center;
    }
    .edition {
        display: flex;
        justify-content: center;
        text-align: center;
        flex-direction: column;
        margin-bottom: 50vh;
    }

    @media (max-width: 600px) {
        .edition {
            padding: 0 2rem 0 2rem;
        }
    }
    @media (min-width: 600px) {
        .edition {
            padding: 0 4rem 0 4rem;
        }
    }

    .backgroundDiv {
        position: relative;
        height: 100%;
        background-image: linear-gradient(
            rgba(5, 11, 3, 0.8) 0%,
            rgba(5, 11, 3, 1) 70%
        );
        overflow: hidden;
        backface-visibility: hidden;
    }

    .backgroundDiv::before {
        content: "";
        position: absolute;
        margin: 1px 1px 1px 1px;
        width: 101%;
        height: 99%;
        background-image: url("/teamPhotos/sideProfileOfMagazines.png");
        background-size: cover;
        background-position: center;
        background-repeat: no-repeat;
        z-index: -1;
    }

    .announcement-container {
        width: calc(100% - 8rem);
        overflow: hidden;
        white-space: nowrap;
        margin-left: 4rem;
        margin-right: 4rem;
    }
    .announcement-inner {
        animation: horizontalScroll 10s linear infinite;
        display: flex;
        gap: 2rem;
    }

    .announcement-inner span {
        font-family: "Inter";
        font-size: 2.369rem;
        letter-spacing: -0.05rem;
        color: antiquewhite;
    }

    @keyframes horizontalScroll {
        0% {
            transform: translateX(0%);
        }
        100% {
            transform: translateX(-50%);
        }
    }
</style>
