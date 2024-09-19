<script>
  import { useMousePosition } from "@svelteuidev/composables";
  const [position, ref] = useMousePosition();
  $: ({ x, y } = $position);
</script>

<div class="issue">
  <a href="/5.1" style="flex-basis: 100%;">Volume 5 Issue 1</a>
  <div
    use:ref
    class="subbox"
    style="flex-basis: 100%; --pagex: {x}px; --pagey: {y}px;"
  >
    <h2 style="color: var(--primary-color);">ARTICLES</h2>
    <div class="grid-container">
      <div class="grid-item-title">The Next Frontier</div>
      <div class="grid-item-author">Derek Zuo</div>
      <div class="grid-item-title">The LZR Racer: SpeedNo</div>
      <div class="grid-item-author">Oneal Wang</div>
      <div class="grid-item-title">The Speed of Sound Sucks</div>
      <div class="grid-item-author">Aaron Dong</div>
      <div class="grid-item-title">Designer Skies</div>
      <div class="grid-item-author">Danny Al-Ali</div>
      <div class="grid-item-title">
        Special Relativity is Pretty Dang Special
      </div>
      <div class="grid-item-author">Justin Kline</div>
      <div class="grid-item-title">Living Robots</div>
      <div class="grid-item-author">Jacob Lynn</div>
      <div class="grid-item-title">Nature's Blueprint for Innovative Design</div>
      <div class="grid-item-author">Kevin Hu</div>
    </div>
  </div>
  <div
    use:ref
    class="subbox"
    style="flex-grow: 1; --pagex: {x}px; --pagey: {y}px; "
  >
    <h2 style="color: var(--primary-color);">EDITORS</h2>
    <ul>
      <li>Kevin Peng (EIC)</li>
      <li>Frank Lin</li>
      <li>Jacob Lynn</li>
      <li>Derek Zuo</li>
    </ul>
  </div>
  <div
    use:ref
    class="subbox"
    style="flex-grow: 1; --pagex: {x}px; --pagey: {y}px;"
  >
    <h2 style="color: var(--primary-color);">GRAPHIC DESIGNERS</h2>
    <ul style="text-align: center;">
      <li>Frank Lin (Lead)</li>
      <li>Kevin Peng</li>
      <li>Danny Al-Ali</li>
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
