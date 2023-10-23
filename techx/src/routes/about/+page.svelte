<script>
  import { Parallax, ParallaxLayer } from "svelte-parallax";
  let windowHeight = 0;
  import MediaQuery from "../../MediaQuery.svelte";

  import Edition32 from "./archive3.2.svelte";
  import Edition31 from "./archive3.1.svelte";
  import Edition22 from "./archive2.2.svelte";
  import Edition21 from "./archive2.1.svelte";
  import Edition13 from "./archive1.3.svelte";
  let totalNumEditions = 6;
</script>

<svelte:window bind:outerHeight={windowHeight} />

<div class="container">
  <Parallax sections={totalNumEditions + 1} sectionHeight={1 * windowHeight}>
    <ParallaxLayer
      rate={1}
      offset={0}
      style="
              display: flex; 
              justify-content: center;
              align-content: center; 
              flex-direction: column;
              z-index: 0;
          "
    >
      <h1 style="text-align: center;">Archives</h1>
    </ParallaxLayer>
    <ParallaxLayer rate={0.5} offset={totalNumEditions - 5}>
      <div class="edition">
        <Edition32 />
      </div>
    </ParallaxLayer>
    <ParallaxLayer rate={0.5} offset={totalNumEditions - 4}>
      <div class="edition">
        <Edition31 />
      </div>
    </ParallaxLayer>
    <ParallaxLayer rate={0.5} offset={totalNumEditions - 3}>
      <div class="edition">
        <Edition22 />
      </div>
    </ParallaxLayer>
    <ParallaxLayer rate={0.5} offset={totalNumEditions - 2}>
      <div class="edition">
        <Edition21 />
      </div>
    </ParallaxLayer>
    <ParallaxLayer rate={0.5} offset={totalNumEditions - 1}>
      <div class="edition">
        <Edition21 />
      </div>
    </ParallaxLayer>
    <ParallaxLayer rate={0.5} offset={totalNumEditions}>
      <div class="edition">
        <Edition13 />
      </div>
    </ParallaxLayer>

    <MediaQuery query="(min-width: 600px)" let:matches>
      {#if matches}
        <ParallaxLayer offset={0} rate={0.7} style="z-index: -1;">
          <div style="width: 100%;">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="100%"
              height="2000"
              viewBox="0 0 904 2000"
              preserveAspectRatio="none"
            >
              <radialGradient
                id="G2"
                cx="50%"
                cy="50%"
                r="50%"
                fx="50%"
                fy="50%"
              >
                <stop
                  offset="0%"
                  style="stop-color:var(--primary-color);    stop-opacity:0.4"
                />
                <stop
                  offset="100%"
                  style="stop-color:var(--primary-color); stop-opacity:0"
                />
              </radialGradient>
              <ellipse cx="100" cy="100" rx="400" ry="400" fill="url(#G2)" />

              <radialGradient
                id="G3"
                cx="50%"
                cy="50%"
                r="50%"
                fx="50%"
                fy="50%"
              >
                <stop
                  offset="0%"
                  style="stop-color:var(--darker-accent);    stop-opacity:0.3"
                />
                <stop
                  offset="100%"
                  style="stop-color:var(--beige); stop-opacity:0"
                />
              </radialGradient>
              <ellipse cx="100%" cy="30rem" rx="300" ry="500" fill="url(#G3)" />
            </svg>
          </div>
        </ParallaxLayer>

        <ParallaxLayer offset={1} rate={1.5} style="z-index: -1;">
          <svg
            class="gr1"
            xmlns="http://www.w3.org/2000/svg"
            width="100%"
            height="2000"
            viewBox="0 0 904 2000"
            fill="url(#gradient2)"
            preserveAspectRatio="none"
          >
            <filter id="grain">
              <feTurbulence
                type="fractalNoise"
                baseFrequency="3"
                stitchTiles="stitch"
              />
              <feColorMatrix
                in="colorNoise"
                type="matrix"
                values="1 0 0 0 0 0 1 0 0 0 0 0 1 0 0 0 0 0 1 0"
              />
              <feComposite
                operator="in"
                in2="SourceGraphic"
                result="monoNoise"
              />
              <feBlend in="SourceGraphic" in2="monoNoise" mode="hard-light" />
            </filter>

            <path
              filter="url(#grain)"
              d="M44.3,-28.5C57.8,-18.4,69.4,0,65.3,13.6C61.1,27.1,41.2,35.8,22.7,43.3C4.1,50.8,-13.2,57.1,-27.8,52.2C-42.3,47.3,-54.1,31.2,-54.1,16.6C-54.1,1.9,-42.3,-11.2,-31.3,-20.7C-20.3,-30.1,-10.2,-35.9,2.6,-38C15.4,-40.1,30.8,-38.5,44.3,-28.5Z"
              transform="scale(3 5) translate(250 200) rotate(0)"
            />

            <linearGradient id="gradient2">
              <stop stop-color="var(--primary-color)" offset="30%" />
              <stop stop-color="var(--primary-accent)" offset="100%" />
            </linearGradient>
          </svg>
        </ParallaxLayer>
        <ParallaxLayer offset={1} rate={1} style="z-index: -1;">
          <svg
            class="gr1"
            xmlns="http://www.w3.org/2000/svg"
            width="100%"
            height="2000"
            viewBox="0 0 904 2000"
            fill="url(#gradient2)"
            preserveAspectRatio="none"
          >
            <filter id="grain">
              <feTurbulence
                type="fractalNoise"
                baseFrequency="3"
                stitchTiles="stitch"
              />
              <feColorMatrix
                in="colorNoise"
                type="matrix"
                values="1 0 0 0 0 0 1 0 0 0 0 0 1 0 0 0 0 0 1 0"
              />
              <feComposite
                operator="in"
                in2="SourceGraphic"
                result="monoNoise"
              />
              <feBlend in="SourceGraphic" in2="monoNoise" mode="hard-light" />
            </filter>

            <path
              filter="url(#grain)"
              d="M44.3,-28.5C57.8,-18.4,69.4,0,65.3,13.6C61.1,27.1,41.2,35.8,22.7,43.3C4.1,50.8,-13.2,57.1,-27.8,52.2C-42.3,47.3,-54.1,31.2,-54.1,16.6C-54.1,1.9,-42.3,-11.2,-31.3,-20.7C-20.3,-30.1,-10.2,-35.9,2.6,-38C15.4,-40.1,30.8,-38.5,44.3,-28.5Z"
              transform="scale(4 5) translate(0 70) rotate(180)"
            />

            <linearGradient id="gradient2">
              <stop stop-color="rgba(101,55,252)" offset="30%" />
              <stop stop-color="rgba(252,101,11)" offset="100%" />
            </linearGradient>
          </svg>
        </ParallaxLayer>
      {/if}
    </MediaQuery>

    <MediaQuery query="(max-width: 600px)" let:matches>
      {#if matches}
        <ParallaxLayer offset={0} rate={0.7} style="z-index: -1;">
          <div style="width: 100%;">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="100%"
              height="2000"
              viewBox="0 0 904 2000"
              preserveAspectRatio="none"
            >
              <radialGradient
                id="G2"
                cx="50%"
                cy="50%"
                r="50%"
                fx="50%"
                fy="50%"
              >
                <stop
                  offset="0%"
                  style="stop-color:var(--primary-color);    stop-opacity:0.4"
                />
                <stop
                  offset="100%"
                  style="stop-color:var(--primary-color); stop-opacity:0"
                />
              </radialGradient>
              <ellipse cx="100" cy="100" rx="400" ry="400" fill="url(#G2)" />

              <radialGradient
                id="G3"
                cx="50%"
                cy="50%"
                r="50%"
                fx="50%"
                fy="50%"
              >
                <stop
                  offset="0%"
                  style="stop-color:var(--darker-accent);    stop-opacity:0.3"
                />
                <stop
                  offset="100%"
                  style="stop-color:var(--beige); stop-opacity:0"
                />
              </radialGradient>
              <ellipse cx="100%" cy="30rem" rx="300" ry="500" fill="url(#G3)" />
            </svg>
          </div>
        </ParallaxLayer>

        <ParallaxLayer offset={1} rate={1.5} style="z-index: -1;">
          <svg
            class="gr1"
            xmlns="http://www.w3.org/2000/svg"
            width="100%"
            height="2000"
            viewBox="0 0 904 2000"
            fill="url(#gradient2)"
            preserveAspectRatio="none"
          >
            <filter id="grain">
              <feTurbulence
                type="fractalNoise"
                baseFrequency="3"
                stitchTiles="stitch"
              />
              <feColorMatrix
                in="colorNoise"
                type="matrix"
                values="1 0 0 0 0 0 1 0 0 0 0 0 1 0 0 0 0 0 1 0"
              />
              <feComposite
                operator="in"
                in2="SourceGraphic"
                result="monoNoise"
              />
              <feBlend in="SourceGraphic" in2="monoNoise" mode="hard-light" />
            </filter>

            <path
              filter="url(#grain)"
              d="M44.3,-28.5C57.8,-18.4,69.4,0,65.3,13.6C61.1,27.1,41.2,35.8,22.7,43.3C4.1,50.8,-13.2,57.1,-27.8,52.2C-42.3,47.3,-54.1,31.2,-54.1,16.6C-54.1,1.9,-42.3,-11.2,-31.3,-20.7C-20.3,-30.1,-10.2,-35.9,2.6,-38C15.4,-40.1,30.8,-38.5,44.3,-28.5Z"
              transform="scale(3 2) translate(300 250) rotate(0)"
            />

            <linearGradient id="gradient2">
              <stop stop-color="var(--primary-color)" offset="30%" />
              <stop stop-color="var(--primary-accent)" offset="100%" />
            </linearGradient>
          </svg>
        </ParallaxLayer>
        <ParallaxLayer offset={1} rate={1} style="z-index: -1;">
          <svg
            class="gr1"
            xmlns="http://www.w3.org/2000/svg"
            width="100%"
            height="2000"
            viewBox="0 0 904 2000"
            fill="url(#gradient2)"
            preserveAspectRatio="none"
          >
            <filter id="grain">
              <feTurbulence
                type="fractalNoise"
                baseFrequency="3"
                stitchTiles="stitch"
              />
              <feColorMatrix
                in="colorNoise"
                type="matrix"
                values="1 0 0 0 0 0 1 0 0 0 0 0 1 0 0 0 0 0 1 0"
              />
              <feComposite
                operator="in"
                in2="SourceGraphic"
                result="monoNoise"
              />
              <feBlend in="SourceGraphic" in2="monoNoise" mode="hard-light" />
            </filter>

            <path
              filter="url(#grain)"
              d="M44.3,-28.5C57.8,-18.4,69.4,0,65.3,13.6C61.1,27.1,41.2,35.8,22.7,43.3C4.1,50.8,-13.2,57.1,-27.8,52.2C-42.3,47.3,-54.1,31.2,-54.1,16.6C-54.1,1.9,-42.3,-11.2,-31.3,-20.7C-20.3,-30.1,-10.2,-35.9,2.6,-38C15.4,-40.1,30.8,-38.5,44.3,-28.5Z"
              transform="scale(3 2) translate(0 70) rotate(180)"
            />

            <linearGradient id="gradient2">
              <stop stop-color="rgba(101,55,252)" offset="30%" />
              <stop stop-color="rgba(252,101,11)" offset="100%" />
            </linearGradient>
          </svg>
        </ParallaxLayer>
      {/if}
    </MediaQuery>
  </Parallax>
</div>

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
    padding: 0 8rem 0 8rem;
  }
</style>
