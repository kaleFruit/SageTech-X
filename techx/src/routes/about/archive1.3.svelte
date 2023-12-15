<script>
  import { useMousePosition } from "@svelteuidev/composables";
  const [position, ref] = useMousePosition();
  $: ({ x, y } = $position);
</script>

<div class="issue">
  <a href="/1.3" style="flex-basis: 100%;">Volume 1 Issue 3</a>
  <div
    use:ref
    class="subbox"
    style="flex-basis: 100%; --pagex: {x}px; --pagey: {y}px;"
  >
    <h2 style="color: var(--primary-color);">ARTICLES</h2>
    <div class="grid-container">
      <div class="grid-item-title">Robots Change Food Industry</div>
      <div class="grid-item-author">Nic Eimani</div>
      <div class="grid-item-title">Real-Life Warp Drive?</div>
      <div class="grid-item-author">Katherine Robertson</div>
      <div class="grid-item-title">
        Probability of an AI Doctor in the Future
      </div>
      <div class="grid-item-author">Minki Shin</div>
      <div class="grid-item-title">USPS - Electrified</div>
      <div class="grid-item-author">Ridwan Simjee</div>
      <div class="grid-item-title">
        What is OCD? Destigmatizing Mental Health
      </div>
      <div class="grid-item-author">Nic Eimani</div>
      <div class="grid-item-title">
        The Astounding Intracies of Slapshot: Rebound
      </div>
      <div class="grid-item-author">Peter Huang</div>
      <div class="grid-item-title">Sony WH-100MX4 Headphone Review</div>
      <div class="grid-item-author">Minki Shin</div>
    </div>
  </div>
  <div
    use:ref
    class="subbox"
    style="flex-grow: 1; --pagex: {x}px; --pagey: {y}px; "
  >
    <h2 style="color: var(--primary-color);">EDITORS</h2>
    <ul>
      <li>Minki Shin (EIC)</li>
      <li>Nico Luo</li>
      <li>Keyon Sabahi</li>
    </ul>
  </div>
  <div
    use:ref
    class="subbox"
    style="flex-grow: 1; --pagex: {x}px; --pagey: {y}px;"
  >
    <h2 style="color: var(--primary-color);">GRAPHIC DESIGNERS</h2>
    <ul style="text-align: center;">
      <li>Minki Shin</li>
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
