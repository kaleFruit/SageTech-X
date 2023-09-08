<nav>
  <span style="text-align: right; flex-basis: 45%;"><a href="/">HOME</a> </span>
  <span style="text-align: left;  flex-basis: 45%;"
    ><a href="/about">ARCHIVES</a></span
  >
</nav>
<img
  src="logo_white.svg"
  alt="logo"
  height="30px"
  width="30px"
  style="position: absolute; left: 0; right: 0; margin: auto; top: 0.5rem;"
/>
<slot />

<svelte:head>
  <!-- <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link
    rel="preconnect"
    href="https://fonts.gstatic.com"
    crossorigin="anonymous"
  />
  <link
    href="https://fonts.googleapis.com/css2?family=Bodoni+Moda:opsz@6..96&display=swap"
    rel="stylesheet"
  /> -->
  <link
    rel="stylesheet"
    href="https://fonts.googleapis.com/css2?family=Lato&family=Mulish"
  />
  <style>
    div:nth-child(1) {
      font-family: "Lato", serif;
    }
    div:nth-child(2) {
      font-family: "Mulish", serif;
    }
  </style>
</svelte:head>

<style>
  :global(:root) {
    --primary-color: #5fc131;
    --primary-accent: #005c53;
    --darker-accent: #00ff77;
    --lime: #dbf227;
    --beige: #c5be8c;
    color: antiquewhite;
    background-color: rgb(5, 11, 3);
  }
  nav {
    width: 100%;
    display: flex;
    justify-content: center;
    background-color: transparent;
    border-radius: 0.5rem;
    padding-top: 0.5rem;
    padding-bottom: 0.5rem;
    gap: 75px;
  }
  a {
    position: relative;
    text-decoration: none;
    color: antiquewhite;
    font-family: "Courier New", Courier, monospace;
    font-size: 1rem;
  }
</style>
