<script>
  import { onMount } from "svelte";
  import { navbarHeight } from "./store.js";
  let navbarElement = 0;
  onMount(() => {
    navbarHeight.set(navbarElement.offsetHeight);
  });
</script>

<nav bind:this={navbarElement} data-sveltekit-reload>
  <img src="logo_white.svg" alt="logo" height="20px" width="20px" />
  <a href="/">HOME</a>
  <a href="/about">ARCHIVES</a>
</nav>

<slot />

<svelte:head>
  <title>Sage Tech-X Magazine</title>
  <link
    rel="stylesheet"
    href="https://fonts.googleapis.com/css2?family=Inter"
  />
</svelte:head>

<style>
  :global(:root) {
    --primary-color: rgb(114, 140, 88);
    --primary-color-rgb: 114, 140, 88;
    --primary-accent: #93a680;
    --darker-accent: rgb(102, 140, 63);
    --darker-accent-rgb: 102, 140, 63;
    --lime: #dbf227;
    --beige: #c5be8c;
    --black: rgb(13, 13, 13);
    color: antiquewhite;
    background-color: var(--black);
  }

  :global(html) {
    font-size: 10px;
  }
  :global(body) {
    margin: 0;
  }
  :global(p) {
    font-size: 1rem;
    font-family: "Inter";
    color: antiquewhite;
    line-height: 110%;
  }

  @media (min-width: 600px) {
    :global(html) {
      font-size: 16px;
    }
  }

  :global(h1) {
    font-family: "Inter";
    line-height: 120%;
    font-size: 5.61rem;
    letter-spacing: 0.05rem;
    color: antiquewhite;
    margin: 0;
  }
  :global(h2) {
    font-family: "Inter";
    line-height: 120%;
    font-size: 4.209rem;
    letter-spacing: 0.05rem;
    color: antiquewhite;
  }
  :global(h3) {
    font-family: "Inter";
    line-height: 120%;
    font-size: 3.157rem;
    letter-spacing: -0.05rem;
    color: antiquewhite;
  }
  :global(h4) {
    font-family: "Inter";
    line-height: 120%;
    font-size: 2.369rem;
    letter-spacing: -0.05rem;
    color: antiquewhite;
  }

  :global(p) {
    font-size: 1rem;
    line-height: 200%;
  }

  nav {
    display: flex;
    justify-content: left;
    background-color: transparent;
    align-items: center;
    padding-top: 1rem;
    padding-bottom: 1rem;
    padding-left: 1rem;
    margin: 0;
    border-radius: 0.5rem;
    gap: 1rem;
    position: fixed;
    z-index: 100;
    width: 100vw;
    top: 0;
  }
  a {
    position: relative;
    transition: transform 0.3s ease-in-out;
    text-decoration: none;
    color: antiquewhite;
    font-family: "Inter";
    font-size: 0.75rem;
    transform-origin: center;
    transform: scale(1);
    text-shadow: var(--black) 1px 0 10px;
  }
  a:hover {
    transform: scale(1.1);
  }
</style>
