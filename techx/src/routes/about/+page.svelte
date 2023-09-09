<script>
  import { Parallax, ParallaxLayer } from "svelte-parallax";
  let windowHeight = 0;
  import MediaQuery from "/src/MediaQuery.svelte";

  import { useMousePosition } from "@svelteuidev/composables";
  const [position, ref] = useMousePosition();
  $: ({ x, y } = $position);
</script>

<svelte:window bind:outerHeight={windowHeight} />

<div class="container">
  <Parallax sections={3} sectionHeight={1 * windowHeight}>
    <ParallaxLayer
      rate={1}
      offset={0}
      style="
              display: flex; 
              justify-content: center;
              align-content: center; 
              flex-direction: column;
              z-index: 1;
          "
    >
      <h1 style="text-align: center;">Archives</h1>
    </ParallaxLayer>
    <ParallaxLayer
      rate={0.5}
      offset={1}
      style="
    display: flex;
    justify-content: center;
    text-align: center;
    flex-direction: column;
    padding: 0 8rem 0 8rem;
    z-index: 3;
  "
    >
      <div class="issue">
        <a href="/3.1" style="flex-basis: 100%;">Volume 3 Issue 2</a>
        <div
          use:ref
          class="subbox"
          style="flex-basis: 100%; --pagex: {x}px; --pagey: {y}px;"
        >
          <h2 style="color: var(--darker-accent);">ARTICLES</h2>
          <div style="display: flex; gap: 2rem; justify-content: center;">
            <ul
              style="list-style-type: none; text-align: right; flex-basis: 45%; "
            >
              <li>The Tau Manifesto</li>
              <li>Pi Day</li>
              <li>Convex Hull and Its Applications</li>
              <li>Printing with a Purpose</li>
              <li>The Convergence of... Autonomous Vehicles</li>
              <li>Nature's Murder Mystery</li>
              <li>Breaking the Barrier</li>
              <li>Snap! Crackle! Pop!</li>
              <li>Solid State Batteries</li>
            </ul>
            <ul
              style="list-style-type: none; text-align: left; flex-basis: 45%;"
            >
              <li>Nicole Ma</li>
              <li>Katherine Robertson</li>
              <li>Melody Yu</li>
              <li>Basim Cheema-Sabir</li>
              <li>Kevin Peng</li>
              <li>Julia Wen</li>
              <li>Derek Zuo</li>
              <li>Oneal Wang</li>
              <li>Kevin Hu</li>
            </ul>
          </div>
        </div>
        <div
          use:ref
          class="subbox"
          style="flex-grow: 1; --pagex: {x}px; --pagey: {y}px; "
        >
          <h2 style="color: var(--beige);">EDITORS</h2>
          <ul>
            <li>Phoebe Pan</li>
            <li>Katherine Robertson</li>
            <li>Marcus Yoo</li>
          </ul>
        </div>
        <div
          use:ref
          class="subbox"
          style="flex-grow: 1; --pagex: {x}px; --pagey: {y}px;"
        >
          <h2 style="color: var(--lime);">GRAPHIC DESIGNERS</h2>
          <ul style="text-align: center;">
            <li>Katherine Robertson</li>
            <li>Marcus Yoo</li>
          </ul>
        </div>
      </div></ParallaxLayer
    >
    <MediaQuery query="(min-width: 600px)" let:matches>
      {#if matches}
        <ParallaxLayer offset={0} rate={0.7}>
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

        <ParallaxLayer offset={1} rate={1.5}>
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
        <ParallaxLayer offset={1} rate={1}>
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
        <ParallaxLayer offset={0} rate={0.7}>
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

        <ParallaxLayer offset={1} rate={1.5}>
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
        <ParallaxLayer offset={1} rate={1}>
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
  .issue {
    display: flex;
    justify-content: space-between;
    gap: 2rem;
    flex-wrap: wrap;
    color: antiquewhite;
    padding: 2rem;
    text-align: center;
    border: 0.3rem solid rgba(255, 255, 255, 0.2);
    border-radius: 1rem;
    background-color: #2e2e2e34;
    box-shadow: 0 0 0.2rem rgb(255, 255, 255, 0.4);
  }

  .subbox {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-content: center;
    border: 0.1rem solid rgba(255, 255, 255, 0.423);
    border-radius: 1rem;
    background-color: #2e2e2e34;
    padding: 1rem;
  }

  .subbox:hover {
    border-radius: 1rem;
    background-origin: border-box;
    background-image: radial-gradient(
      circle at var(--pagex) var(--pagey),
      #b7ff003f,
      transparent 50%
    );
  }

  h2 {
    color: antiquewhite;
    font-family: Lato;
    text-align: center;
    font-size: 1.3rem;
  }
  a {
    color: antiquewhite;
    font-family: Lato;
    text-align: center;
    font-size: 3rem;
    text-decoration: none;
  }
  ul {
    color: antiquewhite;
    font-size: 1rem;
    line-height: 150%;
    font-family: Lato;
    list-style-type: none;
    text-decoration: none;
    padding: 0;
    margin: 0;
  }
  .container {
    width: 100%;
    height: 100%;
    justify-content: center;
    align-items: center;
  }
</style>
