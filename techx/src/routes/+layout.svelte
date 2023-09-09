<nav>
  <img src="logo_white.svg" alt="logo" height="30px" width="30px" />
  <a href="/">HOME</a>
  <a href="/about">ARCHIVES</a>
</nav>
<slot />

<svelte:head>
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

  :global(html) {
    font-size: 10px;
  }

  @media (min-width: 600px) {
    :global(html) {
      font-size: 16px;
    }
  }

  :global(h1) {
    font-family: Lato;
    line-height: 120%;
    font-size: 6rem;
    letter-spacing: -0.1rem;
    color: antiquewhite;
  }

  :global(p) {
    font-size: 1rem;
    line-height: 150%;
  }

  nav {
    display: flex;
    justify-content: left;
    background-color: transparent;
    align-items: center;
    padding-top: 0.5rem;
    padding-bottom: 0.5rem;
    padding-left: 1rem;
    margin: 0.5rem 0.5rem 0.5rem 0.5rem;
    border-radius: 0.5rem;
    gap: 1rem;
  }
  a {
    position: relative;
    text-decoration: none;
    color: antiquewhite;
    font-family: Lato;
    font-size: 0.75rem;
  }
</style>
