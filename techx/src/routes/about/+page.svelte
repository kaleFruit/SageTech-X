<script>
  import { Parallax, ParallaxLayer } from "svelte-parallax";
  let windowHeight = 0;
  import MediaQuery from "../../MediaQuery.svelte";

  import Edition32 from "./archive3.2.svelte";
  import Edition31 from "./archive3.1.svelte";
  import Edition22 from "./archive2.2.svelte";
  import Edition21 from "./archive2.1.svelte";
  import Edition13 from "./archive1.3.svelte";
  import Edition12 from "./archive1.2.svelte";
  import Edition11 from "./archive1.1.svelte";
  let totalNumEditions = 7;
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
    <ParallaxLayer rate={0.5} offset={totalNumEditions - 6}>
      <div class="edition">
        <Edition32 />
      </div>
    </ParallaxLayer>
    <ParallaxLayer rate={0.5} offset={totalNumEditions - 5}>
      <div class="edition">
        <Edition31 />
      </div>
    </ParallaxLayer>
    <ParallaxLayer rate={0.5} offset={totalNumEditions - 4}>
      <div class="edition">
        <Edition22 />
      </div>
    </ParallaxLayer>
    <ParallaxLayer rate={0.5} offset={totalNumEditions - 3}>
      <div class="edition">
        <Edition21 />
      </div>
    </ParallaxLayer>
    <ParallaxLayer rate={0.5} offset={totalNumEditions - 2}>
      <div class="edition">
        <Edition13 />
      </div>
    </ParallaxLayer>
    <ParallaxLayer rate={0.5} offset={totalNumEditions - 1}>
      <div class="edition">
        <Edition12 />
      </div>
    </ParallaxLayer>
    <ParallaxLayer rate={0.5} offset={totalNumEditions}>
      <div class="edition">
        <Edition11 />
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

        <ParallaxLayer offset={1.5} rate={1.5} style="z-index: -1;">
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
                baseFrequency="6"
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
                baseFrequency="6"
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

        <ParallaxLayer offset={2} rate={1.8} style="z-index: -1;">
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
                baseFrequency="6"
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
              d="M46.1,-53.2C60.2,-43.1,72.4,-29,76.2,-12.6C80,3.7,75.5,22.3,64.5,33.4C53.5,44.5,36.1,48,19.4,54.6C2.7,61.3,-13.4,71.2,-29.9,70.3C-46.3,69.4,-63.1,57.8,-70.3,42.1C-77.5,26.5,-75.1,6.8,-70.1,-10.7C-65,-28.3,-57.4,-43.8,-45.3,-54.2C-33.1,-64.7,-16.6,-70.2,-0.3,-69.8C16,-69.5,32,-63.3,46.1,-53.2Z"
              transform="scale(3 4) translate(100 200) rotate(0)"
            />

            <linearGradient id="gradient2">
              <stop stop-color="var(--primary-color)" offset="30%" />
              <stop stop-color="var(--primary-accent)" offset="100%" />
            </linearGradient>
          </svg>
        </ParallaxLayer>

        <ParallaxLayer offset={3} rate={2} style="z-index: -1;">
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
                baseFrequency="6"
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
              d="M42.8,-50.5C57.2,-39,71.6,-27.1,78.5,-10.5C85.4,6.1,84.7,27.3,73.6,38.8C62.6,50.2,41,51.9,21.4,59.1C1.9,66.3,-15.8,79,-26.4,74.3C-37,69.7,-40.5,47.6,-44.3,30.6C-48.1,13.7,-52,1.9,-50.9,-9.8C-49.8,-21.5,-43.7,-33.2,-34.4,-45.6C-25.1,-57.9,-12.5,-71,0.9,-72C14.3,-73,28.5,-62,42.8,-50.5Z"
              transform="scale(3 4) translate(250 200) rotate(0)"
            />

            <linearGradient id="gradient2">
              <stop stop-color="var(--primary-color)" offset="30%" />
              <stop stop-color="var(--primary-accent)" offset="100%" />
            </linearGradient>
          </svg>
        </ParallaxLayer>

        <ParallaxLayer offset={4} rate={1.2} style="z-index: -1;">
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
                baseFrequency="6"
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
              d="M42.8,-50.5C57.2,-39,71.6,-27.1,78.5,-10.5C85.4,6.1,84.7,27.3,73.6,38.8C62.6,50.2,41,51.9,21.4,59.1C1.9,66.3,-15.8,79,-26.4,74.3C-37,69.7,-40.5,47.6,-44.3,30.6C-48.1,13.7,-52,1.9,-50.9,-9.8C-49.8,-21.5,-43.7,-33.2,-34.4,-45.6C-25.1,-57.9,-12.5,-71,0.9,-72C14.3,-73,28.5,-62,42.8,-50.5Z"
              transform="scale(3 4) translate(20 200) rotate(0)"
            />

            <linearGradient id="gradient2">
              <stop stop-color="var(--primary-color)" offset="30%" />
              <stop stop-color="var(--primary-accent)" offset="100%" />
            </linearGradient>
          </svg>
        </ParallaxLayer>

        <ParallaxLayer offset={5.3} rate={1} style="z-index: -1;">
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
                baseFrequency="6"
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
              d="M36.8,-47.8C48.3,-34.3,58.3,-23.2,65.8,-7.6C73.3,7.9,78.2,28,70.2,39.4C62.2,50.8,41.4,53.6,23.3,57.2C5.2,60.7,-10,65.1,-24.6,62.2C-39.3,59.3,-53.2,49,-65.2,34.6C-77.2,20.2,-87.1,1.5,-85.5,-16.4C-83.9,-34.3,-70.7,-51.4,-54.5,-64C-38.3,-76.6,-19.2,-84.7,-3.2,-80.8C12.7,-77,25.4,-61.2,36.8,-47.8Z"
              transform="scale(3 3) translate(270 200) rotate(0)"
            />

            <linearGradient id="gradient2">
              <stop stop-color="var(--primary-color)" offset="30%" />
              <stop stop-color="var(--primary-accent)" offset="100%" />
            </linearGradient>
          </svg>
        </ParallaxLayer>
        <ParallaxLayer offset={6} rate={1.3} style="z-index: -1;">
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
                baseFrequency="6"
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
              d="M28.1,-32.6C37.6,-25.5,47.3,-17.8,50.7,-7.6C54,2.5,51,15.1,44.6,25.4C38.2,35.6,28.5,43.5,17.3,47.6C6.1,51.8,-6.6,52.2,-21.5,50.5C-36.5,48.8,-53.9,45,-62.3,34.2C-70.8,23.3,-70.3,5.5,-67.6,-12.3C-64.8,-30,-59.9,-47.8,-48.3,-54.5C-36.6,-61.1,-18.3,-56.8,-4.5,-51.4C9.3,-46,18.6,-39.7,28.1,-32.6Z"
              transform="scale(3 4) translate(50 200) rotate(0)"
            />

            <linearGradient id="gradient2">
              <stop stop-color="var(--primary-accent)" offset="30%" />
              <stop stop-color="var(--lime)" offset="100%" />
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
                baseFrequency="6"
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
                baseFrequency="4"
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
