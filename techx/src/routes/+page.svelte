<script>
  import { Parallax, ParallaxLayer } from "svelte-parallax";
  import Page from "./about/+page.svelte";
  import MediaQuery from "../MediaQuery.svelte";

  import Team from "./team.svelte";

  let windowHeight = 0;
  let windowWidth = 0;
  let styles = {
    primaryColor: "#9fc131",
    primaryAccent: "#005c53",
    darkerAccent: "#00ff77",
    lime: "#dbf227",
    beige: "#d1cf63",
  };
  let pageX = 0;
  let pageY = 0;
  let paths = [
    {
      id: 1,
      form: "M43.5,-58.6C54.2,-52.2,59.2,-36.5,66.5,-20.2C73.8,-3.8,83.4,13.2,80.8,27.8C78.3,42.5,63.5,54.7,47.9,64.5C32.4,74.3,16.2,81.6,2.1,78.7C-12,75.8,-23.9,62.6,-36.6,51.9C-49.3,41.2,-62.6,32.9,-65.5,21.8C-68.4,10.7,-60.8,-3.3,-54.8,-16.6C-48.8,-29.9,-44.4,-42.5,-35.5,-49.5C-26.7,-56.5,-13.3,-57.8,1.5,-60C16.4,-62.1,32.8,-64.9,43.5,-58.6Z",
      pos: [-10, 80],
      color: [styles.primaryAccent, styles.primaryColor],
      rate: 0.5,
      z: -1,
    },
    {
      id: 5,
      form: "M27.5,-46.5C37.1,-42,47.5,-37.7,54.5,-30C61.5,-22.3,65.2,-11.1,61,-2.4C56.9,6.3,44.9,12.7,41.3,26.3C37.6,39.8,42.3,60.7,36.9,67.3C31.4,73.9,15.7,66.3,3.3,60.6C-9.1,55,-18.3,51.2,-29.4,47.9C-40.5,44.5,-53.6,41.5,-53.8,33.6C-54,25.7,-41.3,12.8,-41.2,0.1C-41,-12.7,-53.4,-25.3,-51.3,-30C-49.2,-34.6,-32.6,-31.1,-21.6,-34.9C-10.7,-38.6,-5.3,-49.5,1.8,-52.6C8.9,-55.7,17.8,-51,27.5,-46.5Z",
      pos: [275, 100],
      color: [styles.primaryColor, styles.primaryAccent],
      rate: 0.5,
      z: -1,
    },
    {
      id: 3,
      form: "M60.3,-10.4C69.4,8.6,62.2,42.1,42.9,55.3C23.5,68.5,-7.9,61.3,-32.4,43.8C-56.8,26.2,-74.3,-1.8,-67.7,-17.2C-61.2,-32.7,-30.6,-35.5,-2.5,-34.7C25.6,-33.9,51.1,-29.4,60.3,-10.4Z",
      pos: [280, 350],
      color: [styles.primaryColor, styles.beige],
      rate: 2,
      z: -3,
    },
    {
      id: 6,
      form: "M27.5,-22.4C33.4,-14.5,34.5,-3.2,36.3,16.1C38.1,35.3,40.7,62.6,30.5,70.1C20.3,77.7,-2.7,65.5,-26.1,54.3C-49.4,43,-73.1,32.5,-72.5,20.7C-71.9,8.8,-47,-4.4,-30.9,-14.7C-14.8,-25,-7.4,-32.3,1.7,-33.7C10.8,-35,21.5,-30.4,27.5,-22.4Z",
      pos: [100, 250],
      color: [styles.primaryColor, styles.primaryAccent],
      rate: 1.3,
      z: 0,
    },
  ];
  let scroll = 0;
  let svgShow = false;

  $: if (scroll > 800) {
    svgShow = true;
  }
</script>

<svelte:window
  bind:outerHeight={windowHeight}
  bind:outerWidth={windowWidth}
  bind:scrollY={scroll}
  on:mousemove={(e) => ({ pageX, pageY } = e)}
/>

<div class="container">
  <Parallax sections={4.5} sectionHeight={0.8 * windowHeight}>
    <ParallaxLayer
      rate={1}
      offset={0}
      style="z-index: -2; justify-content: flex-start;"
    >
      <div class="backgroundDiv" />
    </ParallaxLayer>
    <ParallaxLayer
      rate={1}
      offset={0}
      style="
      display: flex; 
      justify-items: center;
      justify-content: center;
      align-content: center;
      align-items: center; 
      flex-direction: column;
      "
    >
      <h1
        style="
        text-align: center;
        padding: 0;
        margin: 0;
        "
      >
        Sage Tech-X
      </h1>
      <h1
        style="
        text-align: center;
        padding: 0;
        margin: 0;
        "
      >
        Magazine
      </h1>
    </ParallaxLayer>
    <ParallaxLayer
      rate={1}
      offset={1}
      style="
            justify-content: flex-start;
            margin-top: 15rem;
            align-items: left;
            font-size: 2rem;
            z-index: 3;
            position: absolute;
            padding-left: 4rem; 
            padding-right: 4rem; 
          "
    >
      <h1 style="text-align: left;">Our mission.</h1>
      <div style="display: flex;">
        <div
          style="
        display: flex;
        flex-basis: 50%;
        flex-direction: column;
        justify-content: space-between;
        max-width: 30rem;
        "
        >
          <div style="display: grid;">
            <div
              style="text-overflow: clip;
              overflow: hidden; 
              width:  {((pageX * 1.5) / windowWidth) * 25}rem; 
              grid-column: 1;
              grid-row: 1;
              height: 100%;
              "
            >
              <p
                style="
              color: black;
              width: 30rem;
              background-color: var(--primary-color);
              padding: 1rem;
              border: 0.1rem solid rgba(255, 255, 255, 1);
              border-radius: 1rem;
              z-index: 0;
              "
              >
                The Sage Tech-X Magazine hopes to inform and engage the Sage
                Hill students and community about the state of STEM, its
                transformative effects on society, and its limitless
                possibilities in the future.
              </p>
            </div>
            <p
              style="
              color: antiquewhite;
              width: 30rem;
              background-color: black;
              padding: 1rem;
              border: 0.1rem solid rgba(255, 255, 255, 1);
              border-radius: 1rem;
              grid-column: 1;
              grid-row: 1;
              z-index: -1;
              "
            >
              The Sage Tech-X Magazine hopes to inform and engage the Sage Hill
              students and community about the state of STEM, its transformative
              effects on society, and its limitless possibilities in the future.
            </p>
          </div>
          <p>
            Started in 2021, Minki Shin (class of 2022) created the Tech-X
            Magazine with the intention to inspire an open and passionate STEM
            community. The magazine gives students the opportunity to share
            their interests and learn from others. The magazine helps students
            develop their scientific communication. Learning how to distill
            complex ideas into more digestable language is an important, yet
            under-practiced, skill among many young STEM students.
          </p>
          <p>
            If you're interested in contributing to the magazine, please contact
            our current editor-in-chief: 24robertsonk@sagehillschool.org.
          </p>
        </div>
      </div>
    </ParallaxLayer>
    <ParallaxLayer
      rate={2}
      offset={2}
      style="
    justify-content: flex-start;
    gap: 2rem;
    align-items: center;
    display: flex;
    flex-direction: column;
    z-index: 3;
    padding-left: 4rem;
    padding-right: 4rem;
  "
    >
      <h1 style="margin: 0;">Meet our team.</h1>
      <p
        style="
        color: antiquewhite;
        max-width: 600px;
        margin: 0;
        text-align: center;
        font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
        "
      >
        The Sage Tech-X team consists of passionate members of the Sage Hill
        community, who write, edit, and design the magazine. Special thanks to
        Mr. Parker, our club advisor!
      </p>
      <Team />
      <div style="display: flex; flex-wrap: wrap; gap: 1rem;">
        <div class="column">
          <img src="teamPhotos/teamPhoto.jpg" alt="photoOfTeam" />
        </div>
        <div class="column">
          <img src="teamPhotos/magazineOnTable.jpg" alt="photoOfTeam" />
        </div>
      </div>
    </ParallaxLayer>

    <MediaQuery query="(min-width: 1150px)" let:matches>
      {#if matches}
        <div class="default">
          {#each paths as pathInfo}
            <ParallaxLayer
              rate={pathInfo.rate}
              offset={0}
              style="
              justify-content: flex-start; 
              z-index: {pathInfo.z};
              "
            >
              <svg
                class="gr1"
                xmlns="http://www.w3.org/2000/svg"
                width="904"
                height="2000"
                viewBox="0 0 904 2000"
                fill="url(#gradient{pathInfo.id})"
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
                  <feBlend
                    in="SourceGraphic"
                    in2="monoNoise"
                    mode="hard-light"
                  />
                </filter>
                <path
                  filter="url(#grain)"
                  d={pathInfo.form}
                  transform="scale(3 4) translate({pathInfo.pos[0]} {pathInfo
                    .pos[1]})"
                />
                <linearGradient id="gradient{pathInfo.id}">
                  <stop stop-color={pathInfo.color[0]} offset="30%" />
                  <stop stop-color={pathInfo.color[1]} offset="100%" />
                </linearGradient>
              </svg>
            </ParallaxLayer>
          {/each}

          <ParallaxLayer offset={0}>
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="904"
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
                  style="stop-color:var(--beige);    stop-opacity:0.1"
                />
                <stop
                  offset="100%"
                  style="stop-color:var(--beige); stop-opacity:0"
                />
              </radialGradient>
              <ellipse cx="150" cy="650" rx="300" ry="400" fill="url(#G2)" />

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
                  style="stop-color:var(--primary-accent);    stop-opacity:0.2"
                />
                <stop
                  offset="100%"
                  style="stop-color:var(--darker-accent); stop-opacity:0"
                />
              </radialGradient>
              <ellipse cx="850" cy="100" rx="300" ry="250" fill="url(#G3)" />
            </svg>
          </ParallaxLayer>
          <ParallaxLayer
            rate={1}
            offset={1}
            style="
            justify-content: flex-start;
            margin-top: 15rem;
            align-items: left;
            font-size: 2rem;
            z-index: 2;
            position: absolute;
          "
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="904"
              height="2000"
              viewBox="0 0 904 2000"
              preserveAspectRatio="none"
              style="position: absolute; z-index: -3;"
            >
              <radialGradient
                id="G4"
                cx="50%"
                cy="50%"
                r="50%"
                fx="50%"
                fy="50%"
              >
                <stop
                  offset="0%"
                  style="stop-color:var(--primary-color);    stop-opacity:0.5"
                />
                <stop
                  offset="100%"
                  style="stop-color:var(--primary-accent); stop-opacity:0"
                />
              </radialGradient>
              <ellipse cx="0" cy="750" rx="500" ry="500" fill="url(#G4)" />

              <radialGradient
                id="G9"
                cx="50%"
                cy="50%"
                r="50%"
                fx="50%"
                fy="50%"
              >
                <stop
                  offset="0%"
                  style="stop-color:var(--darker-accent);    stop-opacity:0.2"
                />
                <stop
                  offset="100%"
                  style="stop-color:var(--lime); stop-opacity:0"
                />
              </radialGradient>
              <ellipse cx="850" cy="400" rx="300" ry="400" fill="url(#G9)" />
            </svg>
          </ParallaxLayer>
          <ParallaxLayer
            rate={1.5}
            offset={1}
            style="
            margin-top: 15rem;
            align-items: right;
            font-size: 2rem;
            z-index: 3;
            position: absolute;
            padding-right: 4rem; 
            padding-top: 17rem;
          "
          >
            <div
              style="float: right; display: grid; justify-items: center;            
              flex-direction: column;"
            >
              <img
                src="teamPhotos/photoofmagazines.jpg"
                alt="logo"
                style="width: 30rem; border-radius: 2rem;"
              />
            </div>
          </ParallaxLayer>
          <ParallaxLayer offset={2} rate={2}>
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="904"
              height="2000"
              viewBox="0 0 904 2000"
              preserveAspectRatio="none"
            >
              <radialGradient
                id="G5"
                cx="50%"
                cy="50%"
                r="50%"
                fx="50%"
                fy="50%"
              >
                <stop
                  offset="0%"
                  style="stop-color:var(--primary-color);    stop-opacity:0.3"
                />
                <stop
                  offset="100%"
                  style="stop-color:var(--beige); stop-opacity:0"
                />
              </radialGradient>
              <ellipse cx="100" cy="550" rx="350" ry="350" fill="url(#G5)" />

              <radialGradient
                id="G8"
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
                  style="stop-color:var(--lime); stop-opacity:0"
                />
              </radialGradient>
              <ellipse cx="850" cy="400" rx="300" ry="400" fill="url(#G8)" />
            </svg>
          </ParallaxLayer>
        </div>
      {/if}
    </MediaQuery>

    <MediaQuery query="(min-width: 600px) and (max-width: 1150px)" let:matches>
      {#if matches}
        <div class="default">
          {#each paths as pathInfo}
            <ParallaxLayer
              rate={pathInfo.rate}
              offset={0}
              style="
              justify-content: flex-start; 
              z-index: {pathInfo.z};
              "
            >
              <svg
                class="gr1"
                xmlns="http://www.w3.org/2000/svg"
                width="904"
                height="2000"
                viewBox="0 0 904 2000"
                fill="url(#gradient{pathInfo.id})"
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
                  <feBlend
                    in="SourceGraphic"
                    in2="monoNoise"
                    mode="hard-light"
                  />
                </filter>
                <path
                  filter="url(#grain)"
                  d={pathInfo.form}
                  transform="scale(3 3) translate({pathInfo.pos[0]} {pathInfo
                    .pos[1]})"
                />
                <linearGradient id="gradient{pathInfo.id}">
                  <stop stop-color={pathInfo.color[0]} offset="30%" />
                  <stop stop-color={pathInfo.color[1]} offset="100%" />
                </linearGradient>
              </svg>
            </ParallaxLayer>
          {/each}

          <ParallaxLayer offset={0}>
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="904"
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
                  style="stop-color:var(--beige);    stop-opacity:0.3"
                />
                <stop
                  offset="100%"
                  style="stop-color:var(--beige); stop-opacity:0"
                />
              </radialGradient>
              <ellipse cx="150" cy="650" rx="300" ry="400" fill="url(#G2)" />

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
                  style="stop-color:var(--primary-accent);    stop-opacity:0.5"
                />
                <stop
                  offset="100%"
                  style="stop-color:var(--darker-accent); stop-opacity:0"
                />
              </radialGradient>
              <ellipse cx="850" cy="100" rx="300" ry="250" fill="url(#G3)" />
            </svg>
          </ParallaxLayer>
          <ParallaxLayer
            rate={1}
            offset={1}
            style="
            justify-content: flex-start;
            margin-top: 15rem;
            align-items: left;
            font-size: 2rem;
            z-index: 2;
            position: absolute;
          "
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="904"
              height="2000"
              viewBox="0 0 904 2000"
              preserveAspectRatio="none"
              style="position: absolute; z-index: -3;"
            >
              <radialGradient
                id="G4"
                cx="50%"
                cy="50%"
                r="50%"
                fx="50%"
                fy="50%"
              >
                <stop
                  offset="0%"
                  style="stop-color:var(--primary-color);    stop-opacity:0.5"
                />
                <stop
                  offset="100%"
                  style="stop-color:var(--primary-accent); stop-opacity:0"
                />
              </radialGradient>
              <ellipse cx="0" cy="750" rx="500" ry="500" fill="url(#G4)" />

              <radialGradient
                id="G9"
                cx="50%"
                cy="50%"
                r="50%"
                fx="50%"
                fy="50%"
              >
                <stop
                  offset="0%"
                  style="stop-color:var(--darker-accent);    stop-opacity:0.2"
                />
                <stop
                  offset="100%"
                  style="stop-color:var(--lime); stop-opacity:0"
                />
              </radialGradient>
              <ellipse cx="850" cy="400" rx="300" ry="400" fill="url(#G9)" />
            </svg>
          </ParallaxLayer>
          <ParallaxLayer offset={2} rate={2}>
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="904"
              height="2000"
              viewBox="0 0 904 2000"
              preserveAspectRatio="none"
            >
              <radialGradient
                id="G5"
                cx="50%"
                cy="50%"
                r="50%"
                fx="50%"
                fy="50%"
              >
                <stop
                  offset="0%"
                  style="stop-color:var(--primary-color);    stop-opacity:0.3"
                />
                <stop
                  offset="100%"
                  style="stop-color:var(--beige); stop-opacity:0"
                />
              </radialGradient>
              <ellipse cx="100" cy="550" rx="350" ry="350" fill="url(#G5)" />

              <radialGradient
                id="G8"
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
                  style="stop-color:var(--lime); stop-opacity:0"
                />
              </radialGradient>
              <ellipse cx="850" cy="400" rx="300" ry="400" fill="url(#G8)" />
            </svg>
          </ParallaxLayer>
        </div>
      {/if}
    </MediaQuery>

    <MediaQuery query="(max-width: 600px)" let:matches>
      {#if matches}
        <ParallaxLayer offset={0}>
          <p style="text-align: center; font-style: italic; color:chartreuse">
            For the best viewing experience, please move to desktop
          </p>
        </ParallaxLayer>
        <ParallaxLayer
          rate={1}
          offset={1}
          style="
                justify-content: flex-start;
                margin-top: 15rem;
                align-items: left;
                font-size: 2rem;
                z-index: 2;
                position: absolute;
              "
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="904"
            height="2000"
            viewBox="0 0 904 2000"
            preserveAspectRatio="none"
            style="position: absolute; z-index: -3;"
          >
            <radialGradient id="G4" cx="50%" cy="50%" r="50%" fx="50%" fy="50%">
              <stop
                offset="0%"
                style="stop-color:var(--primary-color);    stop-opacity:0.5"
              />
              <stop
                offset="100%"
                style="stop-color:var(--primary-accent); stop-opacity:0"
              />
            </radialGradient>
            <ellipse cx="0" cy="500" rx="500" ry="300" fill="url(#G4)" />
          </svg>
        </ParallaxLayer>

        <ParallaxLayer offset={2} rate={2}>
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="904"
            height="2000"
            viewBox="0 0 904 2000"
            preserveAspectRatio="none"
          >
            <radialGradient id="G5" cx="50%" cy="50%" r="50%" fx="50%" fy="50%">
              <stop
                offset="0%"
                style="stop-color:var(--primary-color);    stop-opacity:0.3"
              />
              <stop
                offset="100%"
                style="stop-color:var(--beige); stop-opacity:0"
              />
            </radialGradient>
            <ellipse cx="100" cy="550" rx="350" ry="350" fill="url(#G5)" />

            <radialGradient id="G8" cx="50%" cy="50%" r="50%" fx="50%" fy="50%">
              <stop
                offset="0%"
                style="stop-color:var(--darker-accent);    stop-opacity:0.3"
              />
              <stop
                offset="100%"
                style="stop-color:var(--lime); stop-opacity:0"
              />
            </radialGradient>
            <ellipse cx="850" cy="400" rx="300" ry="400" fill="url(#G8)" />
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

  .gr1 {
    z-index: 1;
    filter: saturate(100%);
  }
  svg {
    width: 100%;
  }
  .column {
    flex: 1;
    max-width: 50%;
  }

  .column img {
    vertical-align: middle;
    width: 100%;
    border-radius: 1rem;
  }
  @media (max-width: 800px) {
    .column {
      flex: 100%;
      max-width: 100%;
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
    width: 99%;
    height: 99%;
    background-image: url("/teamPhotos/sideProfileOfMagazines.png");
    background-size: auto;
    background-position: center;
    background-repeat: no-repeat;
    z-index: -1;
  }
</style>
