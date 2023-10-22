<script>
  import { Parallax, ParallaxLayer } from "svelte-parallax";
  // const modules = import.meta.glob("$lib/3.2/*.jpg", { as: "raw" });
</script>

<Parallax sections={9}>
  <ParallaxLayer
    rate={1}
    offset={0}
    style="
        display: flex; 
        justify-content: center;
        align-items: center; 
        margin-top: 0.5rem;
    "
  >
    <h1 style="text-align: center;">Volume 1 Issue 3</h1>
    <h2>(CURRENTLY UNDER MAINTANENCE)</h2>
  </ParallaxLayer>

  <ParallaxLayer rate={0.5} offset={1}>
    <div style="display: flex; justify-content: center;">
      <img
        class="photo"
        src="3.2/finalTechX2023sem2-part-21024_1.jpg"
        alt="page1"
      />
      <img
        class="photo"
        src="3.2/finalTechX2023sem2-part-31024_1.jpg"
        alt="page1"
      />
    </div>
  </ParallaxLayer>

  <ParallaxLayer rate={0.5} offset={2}>
    <div style="display: flex; justify-content: center;">
      <img
        class="photo"
        src="3.2/finalTechX2023sem2-part-41024_1.jpg"
        alt="page1"
      />
      <img
        class="photo"
        src="3.2/finalTechX2023sem2-part-51024_1.jpg"
        alt="page1"
      />
    </div>
  </ParallaxLayer>

  <ParallaxLayer rate={0.5} offset={3}>
    <div style="display: flex; justify-content: center;">
      <img
        class="photo"
        src="3.2/finalTechX2023sem2-part-61024_1.jpg"
        alt="page1"
      />
      <img
        class="photo"
        src="3.2/finalTechX2023sem2-part-71024_1.jpg"
        alt="page1"
      />
    </div>
  </ParallaxLayer>

  <ParallaxLayer rate={0.5} offset={4}>
    <div style="display: flex; justify-content: center;">
      <img
        class="photo"
        src="3.2/finalTechX2023sem2-part-81024_1.jpg"
        alt="page1"
      />
      <img
        class="photo"
        src="3.2/finalTechX2023sem2-part-91024_1.jpg"
        alt="page1"
      />
    </div>
  </ParallaxLayer>

  <ParallaxLayer rate={0.5} offset={5}>
    <div style="display: flex; justify-content: center;">
      <img
        class="photo"
        src="3.2/finalTechX2023sem2-part-101024_1.jpg"
        alt="page1"
      />
      <img
        class="photo"
        src="3.2/finalTechX2023sem2-part-111024_1.jpg"
        alt="page1"
      />
    </div>
  </ParallaxLayer>

  <ParallaxLayer rate={0.5} offset={6}>
    <div style="display: flex; justify-content: center;">
      <img
        class="photo"
        src="3.2/finalTechX2023sem2-part-121024_1.jpg"
        alt="page1"
      />
      <img
        class="photo"
        src="3.2/finalTechX2023sem2-part-131024_1.jpg"
        alt="page1"
      />
    </div>
  </ParallaxLayer>

  <ParallaxLayer rate={0.5} offset={7}>
    <div style="display: flex; justify-content: center;">
      <img
        class="photo"
        src="3.2/finalTechX2023sem2-part-141024_1.jpg"
        alt="page1"
      />
      <img
        class="photo"
        src="3.2/finalTechX2023sem2-part-151024_1.jpg"
        alt="page1"
      />
    </div>
  </ParallaxLayer>

  <ParallaxLayer rate={0.5} offset={8}>
    <div style="display: flex; justify-content: center;">
      <img
        class="photo"
        src="3.2/finalTechX2023sem2-part-11024_1.jpg"
        alt="page1"
      />
      <img
        class="photo"
        src="3.2/finalTechX2023sem2-part-161024_1.jpg"
        alt="page1"
      />
    </div>
  </ParallaxLayer>
</Parallax>

<style>
  .photo {
    width: 30rem;
  }
  .stars {
    width: var(--size);
    height: var(--size);
    position: absolute;
    left: var(--leftPos);
    top: var(--topPos);
    background: radial-gradient(farthest-side, rgb(255, 252, 209), transparent);
  }
</style>
