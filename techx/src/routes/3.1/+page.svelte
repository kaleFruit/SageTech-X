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
    "
  >
    <h1 style="text-align: center;">Volume 3 Issue 1</h1>
  </ParallaxLayer>

  <ParallaxLayer rate={0.5} offset={1}>
    <div style="display: flex; justify-content: center;">
      <img class="photo" src="3.1/cover.jpg" alt="cover" style="z-index: 1;" />
    </div>
  </ParallaxLayer>
  {#each { length: 6 } as _, j}
    {#each { length: 10 } as _, i}
      <ParallaxLayer
        offset={0}
        rate={-j + Math.random() * 1.5}
        style="z-index: -1"
      >
        <div
          style="position: relative; margin-left: auto; width: 1500px; margin-right: auto;"
        >
          <div
            class="stars"
            style="--size: {Math.random() * 10 + 0.5}px; --leftPos: {i * 140 +
              Math.random() * 60 -
              25}px; --topPos: {j * 100 + Math.random() * 50 - 25}px;"
          />
        </div>
      </ParallaxLayer>
    {/each}
  {/each}
  <ParallaxLayer offset={1} rate={1.5}>
    <img
      src="3.2/3.2supplemental/jwstmodel.png"
      alt="jwst"
      style="width: 250px; float: right; transform: scaleX(-1); margin-top: 20rem;"
    />
  </ParallaxLayer>
  <ParallaxLayer rate={0.5} offset={2}>
    <div style="display: flex; justify-content: center;">
      <img
        class="photo"
        src="3.1/tableofcontents.jpg"
        alt="table of contents"
      />
    </div>
  </ParallaxLayer>

  <ParallaxLayer rate={0.5} offset={3}>
    <div style="display: flex; justify-content: center;">
      <img class="photo" src="3.1/page1.jpg" alt="page1" />
    </div>
  </ParallaxLayer>

  <ParallaxLayer rate={0.5} offset={4}>
    <div style="display: flex; justify-content: center;">
      <img class="photo" src="3.1/page2.jpg" alt="page2" />
    </div>
  </ParallaxLayer>

  <ParallaxLayer rate={0.5} offset={5}>
    <div style="display: flex; justify-content: center;">
      <img class="photo" src="3.1/page3.jpg" alt="page3" />
    </div>
  </ParallaxLayer>

  <ParallaxLayer rate={0.5} offset={6}>
    <div style="display: flex; justify-content: center;">
      <img class="photo" src="3.1/page4.jpg" alt="page4" />
    </div>
  </ParallaxLayer>

  <ParallaxLayer rate={0.5} offset={7}>
    <div style="display: flex; justify-content: center;">
      <img class="photo" src="3.1/page5.jpg" alt="page5" />
    </div>
  </ParallaxLayer>

  <ParallaxLayer rate={0.5} offset={8}>
    <div style="display: flex; justify-content: center;">
      <img class="photo" src="3.1/appendix.jpg" alt="appendix" />
    </div>
  </ParallaxLayer>
</Parallax>

<style>
  .photo {
    width: 60rem;
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
