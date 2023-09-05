<script>
  import { Parallax, ParallaxLayer } from "svelte-parallax";
  import Page from "./about/+page.svelte";
  let windowHeight = 0;
  let styles = {
    primaryColor: "#9fc131",
    primaryAccent: "#005c53",
    darkerAccent: "#00ff77",
    lime: "#dbf227",
    beige: "#d1cf63",
  };
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
      z: 0,
    },

    // {
    //   id: 2,
    //   form: "M20.1,-46.8C22.6,-33.5,18.7,-21,20.8,-13.3C22.9,-5.7,31,-2.8,38.9,4.6C46.8,11.9,54.4,23.9,49.4,26.6C44.4,29.2,26.9,22.6,16.5,25.4C6.2,28.1,3.1,40.1,-5.9,50.3C-14.9,60.6,-29.8,69,-43.2,68C-56.5,67,-68.4,56.7,-66.5,43.8C-64.6,30.9,-49,15.4,-40.1,5.1C-31.2,-5.2,-29,-10.3,-30.7,-22.9C-32.4,-35.5,-38,-55.4,-33.5,-67.6C-29,-79.8,-14.5,-84.1,-2.8,-79.2C8.8,-74.3,17.7,-60.1,20.1,-46.8Z",
    //   pos: [150, 250],
    //   color: ["#eeaa00", "#00aaff"],
    //   rate: 2,
    //   z: -2,
    // },

    {
      id: 3,
      form: "M60.3,-10.4C69.4,8.6,62.2,42.1,42.9,55.3C23.5,68.5,-7.9,61.3,-32.4,43.8C-56.8,26.2,-74.3,-1.8,-67.7,-17.2C-61.2,-32.7,-30.6,-35.5,-2.5,-34.7C25.6,-33.9,51.1,-29.4,60.3,-10.4Z",
      pos: [280, 350],
      color: [styles.primaryColor, styles.beige],
      rate: 2,
      z: -3,
    },

    // {
    //   id: 4,
    //   form: "M41,-40.6C54.5,-27.4,67.9,-13.7,71.7,3.8C75.5,21.3,69.7,42.6,56.2,56.2C42.6,69.7,21.3,75.5,3,72.5C-15.4,69.5,-30.7,57.8,-44.1,44.3C-57.6,30.7,-69.1,15.4,-72.9,-3.8C-76.7,-23,-72.9,-46,-59.5,-59.2C-46,-72.3,-23,-75.5,-4.6,-70.9C13.7,-66.2,27.4,-53.7,41,-40.6Z",
    //   pos: [200, 275],
    //   color: ["#00ff00", "#eeee00"],
    //   rate: 5,
    //   z: 0,
    // },

    {
      id: 6,
      form: "M27.5,-22.4C33.4,-14.5,34.5,-3.2,36.3,16.1C38.1,35.3,40.7,62.6,30.5,70.1C20.3,77.7,-2.7,65.5,-26.1,54.3C-49.4,43,-73.1,32.5,-72.5,20.7C-71.9,8.8,-47,-4.4,-30.9,-14.7C-14.8,-25,-7.4,-32.3,1.7,-33.7C10.8,-35,21.5,-30.4,27.5,-22.4Z",
      pos: [100, 250],
      color: [styles.primaryColor, styles.primaryAccent],
      rate: 1.3,
      z: 0,
    },
    // {
    //   id: 7,
    //   form: "M49.2,-58.6C64.6,-45.8,78.4,-31,78.2,-16.1C78.1,-1.2,64,13.8,51.5,24.5C39.1,35.2,28.3,41.6,14.8,50.9C1.3,60.3,-14.8,72.6,-27.5,70.2C-40.2,67.9,-49.4,50.9,-59.5,34.1C-69.6,17.2,-80.5,0.6,-74.7,-9.9C-68.9,-20.3,-46.5,-24.5,-31.3,-37.4C-16,-50.3,-8,-71.9,4.5,-77.2C16.9,-82.5,33.9,-71.5,49.2,-58.6Z",
    //   pos: [250, 325],
    //   color: ["#ff0022", "#2222ff"],
    //   rate: 2,
    //   z: -1,
    // },
    // {
    //   id: 8,
    //   form: "M28.2,-32.6C41.2,-22.7,59.5,-18.2,67.3,-7C75.1,4.2,72.3,22.2,64.9,39.7C57.4,57.2,45.3,74.2,31.7,73C18.1,71.9,3,52.5,-16.7,45.5C-36.4,38.5,-60.7,43.8,-72.1,35.8C-83.6,27.9,-82.3,6.8,-78.5,-13.7C-74.7,-34.2,-68.4,-54.1,-54.9,-64C-41.4,-73.8,-20.7,-73.6,-6.6,-65.8C7.6,-58,15.2,-42.6,28.2,-32.6Z",
    //   pos: [75, 400],
    //   color: ["#ff0022", "#2222ff"],
    //   rate: 1.3,
    //   z: -1,
    // },
    // {
    //   id: 9,
    //   form: "M55,-58C69.2,-53.6,77.2,-34.3,73,-18.7C68.8,-3.1,52.3,8.8,41.4,20.4C30.5,32.1,25.2,43.5,13.9,54.9C2.5,66.4,-15,77.9,-30.5,75.7C-45.9,73.6,-59.2,57.7,-68.8,40.2C-78.3,22.7,-84,3.4,-76.3,-8.7C-68.5,-20.9,-47.2,-25.9,-32.3,-30.2C-17.3,-34.5,-8.7,-38,5.9,-44.9C20.4,-51.9,40.8,-62.4,55,-58Z",
    //   pos: [250, 400],
    //   color: ["#eeee00", "#ee0000"],
    //   rate: 1.5,
    //   z: -1,
    // },
  ];
</script>

<svelte:window bind:outerHeight={windowHeight} />
<div class="container">
  <Parallax sections={3.5} sectionHeight={0.8 * windowHeight}>
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
        z-index: 2;
        max-width: 40rem;
        "
      >
        Sage Tech-X Magazine
      </h1>
    </ParallaxLayer>
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
              baseFrequency="3"
              stitchTiles="stitch"
            />
            <feColorMatrix
              in="colorNoise"
              type="matrix"
              values="1 0 0 0 0 0 1 0 0 0 0 0 1 0 0 0 0 0 1 0"
            />
            <feComposite operator="in" in2="SourceGraphic" result="monoNoise" />
            <feBlend in="SourceGraphic" in2="monoNoise" mode="hard-light" />
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
        <radialGradient id="G2" cx="50%" cy="50%" r="50%" fx="50%" fy="50%">
          <stop
            offset="0%"
            style="stop-color:var(--beige);    stop-opacity:0.3"
          />
          <stop offset="100%" style="stop-color:var(--beige); stop-opacity:0" />
        </radialGradient>
        <ellipse cx="150" cy="650" rx="300" ry="400" fill="url(#G2)" />

        <radialGradient id="G3" cx="50%" cy="50%" r="50%" fx="50%" fy="50%">
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
      <div
        style="
        padding-left: 4rem; 
        padding-right: 4rem; 
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        position: absolute;
        "
      >
        <h1 style="text-align: left; margin: 0; padding: 0;">Our Mission</h1>
        <p
          style="
          color: antiquewhite;
          padding: 1rem;
          line-height: 150%;
          text-align: center;
          font-size: 20px;
          border: 2px solid rgba(255, 255, 255, 1);
          border-radius: 1rem;
          box-shadow: 0 0 10px rgb(255, 255, 255, 0.4);
          font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
          "
        >
          The Sage Tech-X Magazine hopes to inform and engage the Sage Hill
          students and community about the state of STEM, its transformative
          effects on society, and its limitless possibilities in the future.
        </p>
        <div
          style="
          display: flex;
          flex-direction: row;
          gap: 2rem;
          justify-content: space-between;
          align-content: center;
          "
        >
          <p
            style="
            font-size: 20px;
            display: flex;
            justify-content: center; 
            align-items: center; 
            line-height: 200%;
            text-align: left; 
            padding: 1rem;
            color: antiquewhite;
            text-indent: 1rem;
            border: 5px solid rgba(255, 255, 255, 0.1);
            border-radius: 1rem;
            background-color: #1212127a;
            font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
            flex-basis: 50%;
            "
          >
            Started in 2021, Minki Shin (class of 2022) created the Tech-X
            Magazine with the intention to inspire an open and passionate STEM
            community. The magazine gives students the opportunity to share
            their interests and learn from others. The magazine helps students
            develop their scientific communication. Learning how to distill
            complex ideas into more digestable language is an important, yet
            under-practiced, skill among many young STEM students.
          </p>
          <div
            style="display: flex; flex-basis: 50%; align-content: center; justify-content: center; padding: 1rem;"
          >
            <img src="logo_white.svg" alt="logo" style="max-width: 50%;" />
          </div>
        </div>
        <p
          style="
          color: antiquewhite;
          padding: 1rem;
          line-height: 150%;
          text-align: center;
          font-size: 20px;
          border: 5px solid rgba(255, 255, 255, 0.1);
          border-radius: 1rem;
          background-color: #1212127a;
          font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif
          "
        >
          If you're interested in contributing to the magazine, please contact
          24robertsonk@sagehillschool.org.
        </p>
      </div>
      <svg
        xmlns="http://www.w3.org/2000/svg"
        width="904"
        height="2000"
        viewBox="0 0 904 2000"
        preserveAspectRatio="none"
        style="position: absolute;"
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
        <ellipse cx="0" cy="750" rx="500" ry="500" fill="url(#G4)" />

        <radialGradient id="G9" cx="50%" cy="50%" r="50%" fx="50%" fy="50%">
          <stop
            offset="0%"
            style="stop-color:var(--darker-accent);    stop-opacity:0.2"
          />
          <stop offset="100%" style="stop-color:var(--lime); stop-opacity:0" />
        </radialGradient>
        <ellipse cx="850" cy="400" rx="300" ry="400" fill="url(#G9)" />
      </svg>
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
      <h1 style="margin: 0;">Meet Our Team</h1>
      <p
        style="
          color: antiquewhite;
          max-width: 600px;
          margin: 0;
          line-height: 150%;
          text-align: center;
          font-size: 20px;
          font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
          "
      >
        The Sage Tech-X team consists of passionate members of the Sage Hill
        community, who write, edit, and design the magazine.
      </p>
      <div
        style="
      display: flex; 
      flex-wrap: wrap;
      justify-content: space-between;
      gap: 2rem;
      "
      >
        <div class="role" style="--color:var(--beige); flex-basis: 44%;">
          <h>EDITORS</h>
          <div class="cards">
            <div class="infoCard">
              <h2>Katherine Robertson</h2>
              <p>Years: 2021-Present</p>
              <p>Grade: Senior</p>
            </div>
            <div class="infoCard">
              <h2>Phoebe Pan</h2>
              <p>Years: 2022-Present</p>
              <p>Grade: Senior</p>
            </div>
          </div>
        </div>
        <div class="role" style="--color: var(--lime); flex-basis: 44%;">
          <h>GRAPHIC DESIGNERS</h>
          <div class="cards">
            <div class="infoCard">
              <h2>Marcus Yoo</h2>
              <p>Years: 2021-Present</p>
              <p>Grade: Senior</p>
            </div>
            <div class="infoCard">
              <h2>Jennifer Huang</h2>
              <p>Years: 2022-Present</p>
              <p>Grade: Senior</p>
            </div>
          </div>
        </div>
        <div class="role" style="--color: var(--darker-accent); width: 100%;">
          <h>WRITERS</h>
          <div class="cards">
            <div class="infoCard">
              <h2>Nicole Ma</h2>
              <p>Years: 2022-Present</p>
              <p>Grade: Senior</p>
            </div>
            <div class="infoCard">
              <h2>Kevin Peng</h2>
              <p>Years: 2023-Present</p>
              <p>Grade: Junior</p>
            </div>
            <div class="infoCard">
              <h2>Oneal Wang</h2>
              <p>Years: 2022-Present</p>
              <p>Grade: Junior</p>
            </div>
            <div class="infoCard">
              <h2>Jacob Lynn</h2>
              <p>Years: 2022-Present</p>
              <p>Grade: Junior</p>
            </div>
            <div class="infoCard">
              <h2>Derek Zuo</h2>
              <p>Years: 2022-Present</p>
              <p>Grade: Junior</p>
            </div>
            <div class="infoCard">
              <h2>Julia Wen</h2>
              <p>Years: 2022-Present</p>
              <p>Grade: Senior</p>
            </div>
            <div class="infoCard">
              <h2>Melody Yu</h2>
              <p>Years: 2022-Present</p>
              <p>Grade: Junior</p>
            </div>
            <div class="infoCard">
              <h2>Basim Cheema-Sabir</h2>
              <p>Years: 2022-Present</p>
              <p>Grade: Senior</p>
            </div>
            <div class="infoCard">
              <h2>Alen Zhang</h2>
              <p>Years: 2022-Present</p>
              <p>Grade: Junior</p>
            </div>
            <div class="infoCard">
              <h2>Kai Patragnoni</h2>
              <p>Years: 2022-Present</p>
              <p>Grade: Senior</p>
            </div>
            <div class="infoCard">
              <h2>Kevin Hu</h2>
              <p>Years: 2022-Present</p>
              <p>Grade: Senior</p>
            </div>
          </div>
        </div>
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
        <radialGradient id="G5" cx="50%" cy="50%" r="50%" fx="50%" fy="50%">
          <stop
            offset="0%"
            style="stop-color:var(--primary-color);    stop-opacity:0.3"
          />
          <stop offset="100%" style="stop-color:var(--beige); stop-opacity:0" />
        </radialGradient>
        <ellipse cx="100" cy="550" rx="350" ry="350" fill="url(#G5)" />

        <radialGradient id="G8" cx="50%" cy="50%" r="50%" fx="50%" fy="50%">
          <stop
            offset="0%"
            style="stop-color:var(--darker-accent);    stop-opacity:0.3"
          />
          <stop offset="100%" style="stop-color:var(--lime); stop-opacity:0" />
        </radialGradient>
        <ellipse cx="850" cy="400" rx="300" ry="400" fill="url(#G8)" />
      </svg>
    </ParallaxLayer>
  </Parallax>
</div>

<style>
  h1 {
    font-family: Bodoni Moda;
    font-size: 5rem;
    color: antiquewhite;
  }

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
  .infoCard {
    border: 3px solid rgba(215, 218, 250, 0.343);
    border-radius: 1rem;
    padding: 0.5rem;
    background-color: #1f1f1f;
  }
  .role {
    border: 5px solid rgba(255, 255, 255, 0.1);
    background: #1212127a;
    border-radius: 1rem;
    padding: 1rem;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-content: center;
    flex-direction: column;
  }
  .role h {
    color: var(--color, #ddd);
    font-family: "Courier New", Courier, monospace;
    font-style: bold;
    font-size: 35px;
    text-align: center;
  }

  .cards {
    padding: 1rem;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-content: center;
    gap: 1rem;
  }
  .infoCard h2 {
    color: antiquewhite;
    font-family: "Trebuchet MS", "Lucida Sans Unicode", "Lucida Grande",
      "Lucida Sans", Arial, sans-serif;
    font-size: 20px;
    text-align: left;
    line-height: 100%;
  }
  .infoCard p {
    color: antiquewhite;
    font-family: "Trebuchet MS", "Lucida Sans Unicode", "Lucida Grande",
      "Lucida Sans", Arial, sans-serif;
    font-size: 15px;
    text-align: left;
  }
</style>
