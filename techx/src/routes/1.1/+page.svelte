<script>
  import { Parallax, ParallaxLayer } from "svelte-parallax";
  // const modules = import.meta.glob("$lib/3.2/*.jpg", { as: "raw" });
</script>

<Parallax sections={11}>
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
    <h1 style="text-align: center;">Volume 1 Issue 1</h1>
  </ParallaxLayer>

  <ParallaxLayer rate={0.5} offset={1}>
    <div style="display: flex; justify-content: center;">
      <img class="photo" src="1.1/p1.jpg" alt="front cover" />
      <img class="photo" src="1.1/p20.jpg" alt="back cover" />
    </div>
  </ParallaxLayer>

  <ParallaxLayer rate={0.5} offset={2}>
    <div style="display: flex; justify-content: center;">
      <img class="photo" src="1.1/p2.jpg" alt="page2" />
      <img class="photo" src="1.1/p3.jpg" alt="page3" />
    </div>
  </ParallaxLayer>

  <ParallaxLayer rate={0.5} offset={3}>
    <div style="display: flex; justify-content: center;">
      <img class="photo" src="1.1/p4.jpg" alt="page4" />
      <img class="photo" src="1.1/p5.jpg" alt="page5" />
    </div>
  </ParallaxLayer>

  <ParallaxLayer rate={0.5} offset={4}>
    <div style="display: flex; justify-content: center;">
      <img class="photo" src="1.1/p6.jpg" alt="page6" />
      <img class="photo" src="1.1/p7.jpg" alt="page7" />
    </div>
  </ParallaxLayer>

  <ParallaxLayer rate={0.5} offset={5}>
    <div style="display: flex; justify-content: center;">
      <img class="photo" src="1.1/p8.jpg" alt="page8" />
      <img class="photo" src="1.1/p9.jpg" alt="page9" />
    </div>
  </ParallaxLayer>

  <ParallaxLayer rate={0.5} offset={6}>
    <div style="display: flex; justify-content: center;">
      <img class="photo" src="1.1/p10.jpg" alt="page10" />
      <img class="photo" src="1.1/p11.jpg" alt="page11" />
    </div>
  </ParallaxLayer>

  <ParallaxLayer rate={0.5} offset={7}>
    <div style="display: flex; justify-content: center;">
      <img class="photo" src="1.1/p12.jpg" alt="page12" />
      <img class="photo" src="1.1/p13.jpg" alt="page13" />
    </div>
  </ParallaxLayer>

  <ParallaxLayer rate={0.5} offset={8}>
    <div style="display: flex; justify-content: center;">
      <img class="photo" src="1.1/p14.jpg" alt="page14" />
      <img class="photo" src="1.1/p15.jpg" alt="page15" />
    </div>
  </ParallaxLayer>
  <ParallaxLayer rate={0.5} offset={9}>
    <div style="display: flex; justify-content: center;">
      <img class="photo" src="1.1/p16.jpg" alt="page16" />
      <img class="photo" src="1.1/p17.jpg" alt="page17" />
    </div>
  </ParallaxLayer>
  <ParallaxLayer rate={0.5} offset={10}>
    <div style="display: flex; justify-content: center;">
      <img class="photo" src="1.1/p18.jpg" alt="page18" />
      <img class="photo" src="1.1/p19.jpg" alt="page19" />
    </div>
  </ParallaxLayer>
</Parallax>

<style>
  .photo {
    width: 30rem;
  }
</style>
