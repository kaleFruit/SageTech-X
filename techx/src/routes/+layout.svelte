<nav>
  <ul>
    <li><a href="/">HOME</a></li>
  </ul>
  <ul><img src="logo_white.svg" alt="logo" height="30px" width="30px" /></ul>
  <ul>
    <li><a href="/about">ARCHIVES</a></li>
  </ul>
</nav>
<slot />

<svelte:head>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link
    rel="preconnect"
    href="https://fonts.gstatic.com"
    crossorigin="anonymous"
  />
  <link
    href="https://fonts.googleapis.com/css2?family=Bodoni+Moda:opsz@6..96&display=swap"
    rel="stylesheet"
  />
</svelte:head>

<style>
  nav {
    display: flex;
    justify-content: center;
    align-content: center;
    background-color: transparent;
    gap: 3rem;
    border-radius: 0.5rem;
    padding: 0.25rem;
  }
  a {
    position: relative;
    text-decoration: none;
    color: antiquewhite;
    font-family: "Courier New", Courier, monospace;
    font-size: 1rem;
  }
  ul {
    list-style-type: none;
    position: relative;
    text-align: center;
    margin-top: auto;
    margin-bottom: auto;
    padding: 0;
  }
</style>
