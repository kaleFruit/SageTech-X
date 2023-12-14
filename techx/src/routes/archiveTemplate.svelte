<script>
  import { navbarHeight } from "./store.js";
  import { onMount } from "svelte";
  import Lenis from "@studio-freight/lenis";

  export let photos = [];
  export let edition = "";

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

<div
  style="display: flex; align-items: center; justify-content: center; height: calc(100vh - {$navbarHeight}px); padding-left: 2rem; padding-right: 2rem;"
>
  <h1 style="text-align: center;">{edition}</h1>
</div>
{#each { length: photos.length / 2 } as _, index}
  <div class="page" style="height: calc(100vh - {$navbarHeight}px);">
    <img class="photo" src={photos[2 * index]} alt="pg" />
    <img class="photo" src={photos[2 * index + 1]} alt="pg" />
  </div>
{/each}

<style>
  @media (max-width: 800px) {
    .photo {
      width: 30rem;
      object-fit: contain;
    }
  }
  @media (min-width: 800px) {
    .photo {
      width: 30rem;
      height: auto;
    }
  }
  .page {
    margin-top: 10rem;
    margin-bottom: 10rem;
    width: 100%;
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 0;
  }
</style>
