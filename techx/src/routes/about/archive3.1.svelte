<script>
  import { useMousePosition } from "@svelteuidev/composables";
  const [position, ref] = useMousePosition();
  $: ({ x, y } = $position);
</script>

<div class="issue">
  <a href="/3.1" style="flex-basis: 100%;">Volume 3 Issue 1</a>
  <div
    use:ref
    class="subbox"
    style="flex-basis: 100%; --pagex: {x}px; --pagey: {y}px;"
  >
    <h2 style="color: var(--primary-color);">ARTICLES</h2>
    <div class="grid-container">
      <div class="grid-item-title">The James Webb Telescope</div>
      <div class="grid-item-author">Nicole Ma</div>
      <div class="grid-item-title">How Filming Technology Saved Star Wars</div>
      <div class="grid-item-author">Oneal Wang</div>
      <div class="grid-item-title">VNPs and Extraterrestrial Intelligence</div>
      <div class="grid-item-author">Jacob Lynn</div>
      <div class="grid-item-title">Delicious, Radioactive, Yellowcake</div>
      <div class="grid-item-author">Alen Zhang</div>
      <div class="grid-item-title">Hello World</div>
      <div class="grid-item-author">Katherine Robertson</div>
      <div class="grid-item-title">About AI, Written by AI</div>
      <div class="grid-item-author">Kai Patragnoni</div>
      <div class="grid-item-title">Grete Hermann: The Forgotten Physicist</div>
      <div class="grid-item-author">Nicole Ma</div>
      <div class="grid-item-title">How Godel Broke Math</div>
      <div class="grid-item-author">Nicole Ma</div>
    </div>
  </div>
  <div
    use:ref
    class="subbox"
    style="flex-grow: 1; --pagex: {x}px; --pagey: {y}px; "
  >
    <h2 style="color: var(--primary-color);">EDITORS</h2>
    <ul>
      <li>Katherine Robertson (EIC)</li>
      <li>Phoebe Pan (Co-Editor)</li>
      <li>Marcus Yoo</li>
    </ul>
  </div>
  <div
    use:ref
    class="subbox"
    style="flex-grow: 1; --pagex: {x}px; --pagey: {y}px;"
  >
    <h2 style="color: var(--primary-color);">GRAPHIC DESIGNERS</h2>
    <ul style="text-align: center;">
      <li>Marcus Yoo</li>
      <li>Katherine Robertson</li>
      <li>Jennifer Huang</li>
    </ul>
  </div>
</div>

<style>
  .issue {
    display: flex;
    justify-content: space-between;
    gap: 2rem;
    flex-wrap: wrap;
    color: antiquewhite;
    padding: 2rem;
    text-align: center;
    border: 1px solid rgba(255, 255, 255, 0.2);
    border-radius: 1rem;
    background-color: #2e2e2e34;
    box-shadow: 0 0 0.2rem rgb(255, 255, 255, 0.4);
  }

  .subbox {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-content: center;
    border: 0.1rem solid rgba(255, 255, 255, 0.423);
    border-radius: 1rem;
    background-color: #2e2e2e34;
    padding: 1rem;
  }

  .subbox:hover {
    border-radius: 1rem;
    background-origin: border-box;
    background-image: radial-gradient(
      circle at var(--pagex) var(--pagey),
      rgba(var(--darker-accent-rgb), 0.2),
      transparent 50%
    );
  }

  h2 {
    color: antiquewhite;
    font-family: "Inter";
    text-align: center;
    font-size: 1.3rem;
  }
  a {
    color: antiquewhite;
    font-family: "Inter";
    text-align: center;
    font-size: 3rem;
    text-decoration: underline;
    transform-origin: center;
    transform: scale(1);
    transition: transform 0.5s ease-in-out;
  }
  a:hover {
    transform: scale(1.1);
  }
  ul {
    color: antiquewhite;
    font-size: 1rem;
    line-height: 150%;
    font-family: "Inter";
    list-style-type: none;
    text-decoration: none;
    padding: 0;
    margin: 0;
  }
  .grid-container {
    display: grid;
    column-gap: 3rem;
    row-gap: 0.3rem;
    grid-template-columns: 1fr 1fr;
  }

  .grid-item-title {
    color: antiquewhite;
    font-size: 1rem;
    line-height: 150%;
    font-family: "Inter";
    list-style-type: none;
    text-decoration: none;
    padding: 0;
    margin: 0;
    text-align: right;
  }

  .grid-item-author {
    color: antiquewhite;
    font-size: 1rem;
    line-height: 150%;
    font-family: "Inter";
    list-style-type: none;
    text-decoration: none;
    padding: 0;
    margin: 0;
    text-align: left;
  }
</style>
