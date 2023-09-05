<script>
  import { Parallax, ParallaxLayer } from "svelte-parallax";
  const modules = import.meta.glob("$lib/3.2/*.jpg", { as: "raw" });
  let windowHeight = 0;
  import MediaQuery from "/src/MediaQuery.svelte";
</script>

<svelte:window bind:outerHeight={windowHeight} />

<MediaQuery query="(min-width: 600px)" let:matches>
  {#if matches}
    <div class="default">
      <div class="container">
        <Parallax sections={3} sectionHeight={1 * windowHeight}>
          <ParallaxLayer
            rate={1}
            offset={0}
            style="
            display: flex; 
            justify-content: center;
            align-items: center; 
            flex-direction: column;
            z-index: 1;
        "
          >
            <h1 style="text-align: center;">Archives</h1>
          </ParallaxLayer>

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
                <ellipse
                  cx="100%"
                  cy="30rem"
                  rx="300"
                  ry="500"
                  fill="url(#G3)"
                />
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
          <ParallaxLayer
            rate={0.5}
            offset={1}
            style="
            display: flex;
            justify-content: center;
            text-align: center;
            flex-direction: column;
            padding: 0 8rem 0 8rem;
          "
          >
            <div class="issue">
              <a href="/3.1" style="flex-basis: 100%;">Volume 3 Issue 2</a>
              <div class="subbox" style="flex-basis: 100%;">
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
              <div class="subbox" style="flex-grow: 1; ">
                <h2 style="color: var(--beige);">EDITORS</h2>
                <ul>
                  <li>Phoebe Pan</li>
                  <li>Katherine Robertson</li>
                  <li>Marcus Yoo</li>
                </ul>
              </div>
              <div class="subbox" style="flex-grow: 1;">
                <h2 style="color: var(--lime);">GRAPHIC DESIGNERS</h2>
                <ul style="text-align: center;">
                  <li>Katherine Robertson</li>
                  <li>Marcus Yoo</li>
                </ul>
              </div>
            </div></ParallaxLayer
          >
        </Parallax>
      </div>
    </div>
  {/if}
</MediaQuery>

<MediaQuery query="(max-width: 600px)" let:matches>
  {#if matches}
    <div class="mobile">
      <div class="container">
        <Parallax sections={3} sectionHeight={1 * windowHeight}>
          <ParallaxLayer
            rate={1}
            offset={0}
            style="
            display: flex; 
            justify-content: center;
            align-items: center; 
            flex-direction: column;
            z-index: 1;
        "
          >
            <h1 style="text-align: center;">Archives</h1>
          </ParallaxLayer>

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
                <ellipse
                  cx="100%"
                  cy="30rem"
                  rx="300"
                  ry="500"
                  fill="url(#G3)"
                />
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
          <ParallaxLayer
            rate={0.5}
            offset={1}
            style="
            display: flex;
            justify-content: center;
            text-align: center;
            flex-direction: column;
            padding: 0 2rem 0 2rem;
          "
          >
            <div class="issue">
              <a href="/3.1" style="flex-basis: 100%;">Volume 3 Issue 2</a>
              <div class="subbox" style="flex-basis: 100%;">
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
              <div class="subbox" style="flex-grow: 1; ">
                <h2 style="color: var(--beige);">EDITORS</h2>
                <ul>
                  <li>Phoebe Pan</li>
                  <li>Katherine Robertson</li>
                  <li>Marcus Yoo</li>
                </ul>
              </div>
              <div class="subbox" style="flex-grow: 1;">
                <h2 style="color: var(--lime);">GRAPHIC DESIGNERS</h2>
                <ul style="text-align: center;">
                  <li>Katherine Robertson</li>
                  <li>Marcus Yoo</li>
                </ul>
              </div>
            </div></ParallaxLayer
          >
        </Parallax>
      </div>
    </div>
  {/if}
</MediaQuery>

<style>
  .default .issue {
    display: flex;
    justify-content: space-between;
    gap: 2rem;
    flex-wrap: wrap;
    color: antiquewhite;
    padding: 2rem;
    text-align: center;
    border: 5px solid rgba(255, 255, 255, 0.2);
    border-radius: 25px;
    background-color: #2e2e2e34;
    box-shadow: 0 0 10px rgb(255, 255, 255, 0.4);
  }

  .default .subbox {
    display: flex;
    flex-direction: column;
    padding: 1rem;
    justify-content: center;
    align-content: center;
    border: 5px solid rgba(255, 255, 255, 0.423);
    border-radius: 25px;
    background-color: #2e2e2e34;
  }

  .default h1 {
    font-family: Bodoni Moda;
    font-size: 5rem;
    color: antiquewhite;
    text-align: center;
  }
  .default h2 {
    color: antiquewhite;
    font-family: "Courier New", Courier, monospace;
    font-style: bold;
    font-size: 35px;
    text-align: center;
    line-height: 100%;
  }
  .default a {
    font-size: 5rem;
    text-align: center;
    text-decoration: none;
    line-height: 100%;
    color: antiquewhite;
    margin: 1rem;
  }
  .default ul {
    color: antiquewhite;
    line-height: 150%;
    font-size: 20px;
    font-family: "Trebuchet MS", "Lucida Sans Unicode", "Lucida Grande",
      "Lucida Sans", Arial, sans-serif;
    list-style-type: none;
    text-decoration: none;
    margin: 0;
    padding: 0;
  }

  .mobile .issue {
    display: flex;
    justify-content: space-between;
    gap: 1rem;
    flex-wrap: wrap;
    color: antiquewhite;
    padding: 0.5rem;
    text-align: center;
    border: 1px solid rgba(255, 255, 255, 0.2);
    border-radius: 0.5rem;
    background-color: #2e2e2e34;
    box-shadow: 0 0 10px rgb(255, 255, 255, 0.4);
  }

  .mobile .subbox {
    display: flex;
    flex-direction: column;
    padding: 0.5rem;
    justify-content: center;
    align-content: center;
    border: 1px solid rgba(255, 255, 255, 0.423);
    border-radius: 15px;
    background-color: #2e2e2e34;
  }

  .mobile h1 {
    font-family: Bodoni Moda;
    font-size: 2rem;
    color: antiquewhite;
    text-align: center;
  }
  .mobile h2 {
    color: antiquewhite;
    font-family: "Courier New", Courier, monospace;
    font-style: bold;
    font-size: 15px;
    text-align: center;
    line-height: 100%;
  }
  .mobile a {
    font-size: 2rem;
    text-align: center;
    text-decoration: none;
    line-height: 100%;
    color: antiquewhite;
    margin: 0.2rem;
  }
  .mobile ul {
    color: antiquewhite;
    line-height: 150%;
    font-size: 15px;
    font-family: "Trebuchet MS", "Lucida Sans Unicode", "Lucida Grande",
      "Lucida Sans", Arial, sans-serif;
    list-style-type: none;
    text-decoration: none;
    margin: 0;
    padding: 0;
  }

  .container {
    width: 100%;
    height: 100%;
    justify-content: center;
    align-items: center;
  }
</style>
