<script>
  import { useMousePosition } from "@svelteuidev/composables";
  const [position, ref] = useMousePosition();
  $: ({ x, y } = $position);
</script>

<div class="issue">
  <a href="/4.1" style="flex-basis: 100%;">Volume 4 Issue 1</a>
  <div
    use:ref
    class="subbox"
    style="flex-basis: 100%; --pagex: {x}px; --pagey: {y}px;"
  >
    <h2 style="color: var(--primary-color);">ARTICLES</h2>
    <div class="grid-container">
      <div class="grid-item-title">Unraveling the Yang Mills Theorem</div>
      <div class="grid-item-author">Alen Zhang</div>
      <div class="grid-item-title">You're Not Massive, You're Just Popular</div>
      <div class="grid-item-author">Justin Klein</div>
      <div class="grid-item-title">Unleashing the Power of QML</div>
      <div class="grid-item-author">Bruce Li</div>
      <div class="grid-item-title">Tachyons: The Speed Demons of Physics</div>
      <div class="grid-item-author">Arshaun Oshideri</div>
      <div class="grid-item-title">
        Heavy Light Decomposition and Tree Algorithms
      </div>
      <div class="grid-item-author">Melody Yu</div>
      <div class="grid-item-title">Modeling Compliant Mechanisms</div>
      <div class="grid-item-author">Katherine Robertson</div>
      <div class="grid-item-title">Look Up: Weapons in the Sky</div>
      <div class="grid-item-author">Oneal Wang</div>
      <div class="grid-item-title">Von Neumann Probes Part II and III</div>
      <div class="grid-item-author">Jacob Lynn</div>
      <div class="grid-item-title">Student Project Showcase V0.1</div>
      <div class="grid-item-author">Kevin Peng</div>
      <div class="grid-item-title">
        V2X and LiDAR: Revolutionizing Electric Vehicles
      </div>
      <div class="grid-item-author">Kevin Hu</div>
      <div class="grid-item-title">The Aerodynamics of Formula 1</div>
      <div class="grid-item-author">Kevin Peng</div>
      <div class="grid-item-title">The F-35B</div>
      <div class="grid-item-author">Basim Cheema-Sabir</div>
      <div class="grid-item-title">Bioinformatics: The Future of Medicine</div>
      <div class="grid-item-author">Harriet Lai</div>
      <div class="grid-item-title">Sage Hill Student Club Spotlight V0.1</div>
      <div class="grid-item-author">Derek Zuo</div>
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
      <li>Nicole Ma</li>
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
      <li>Marcus Yoo (Lead)</li>
      <li>Katherine Robertson</li>
      <li>Danny Al-Ali</li>
      <li>Oneal Wang</li>
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
