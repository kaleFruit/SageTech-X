<script>
  import { useMousePosition } from "@svelteuidev/composables";
  const [position, ref] = useMousePosition();
  $: ({ x, y } = $position);
</script>

<div class="issue">
  <a href="/2.1" style="flex-basis: 100%;">Volume 2 Issue 1</a>
  <div
    use:ref
    class="subbox"
    style="flex-basis: 100%; --pagex: {x}px; --pagey: {y}px;"
  >
    <h2 style="color: var(--darker-accent);">ARTICLES</h2>
    <div style="display: flex; gap: 2rem; justify-content: center;">
      <ul style="list-style-type: none; text-align: right; flex-basis: 45%; ">
        <li>Moisture Farming</li>
        <li>AI Art vs. Human Art</li>
        <li>Can AI Diagnose Disease Better than Humans?</li>
        <li>"Right to Repair"</li>
        <li>Varieties in Engineering</li>
        <li>What are Chatbots?</li>
        <li>E Review</li>
      </ul>
      <ul style="list-style-type: none; text-align: left; flex-basis: 45%;">
        <li>Katherine Robertson</li>
        <li>Minki Shin</li>
        <li>Minki Shin</li>
        <li>Ridwan Simjee</li>
        <li>Minki Shin</li>
        <li>Minki Shin</li>
        <li>Keyon Sabahi</li>
      </ul>
    </div>
  </div>
  <div
    use:ref
    class="subbox"
    style="flex-grow: 1; --pagex: {x}px; --pagey: {y}px; "
  >
    <h2 style="color: var(--beige);">EDITORS</h2>
    <ul>
      <li>Minki Shin (EIC)</li>
      <li>Anton Nguyen</li>
      <li>Peter Huang</li>
      <li>Nic Eimani</li>
      <li>Marcus Yoo</li>
    </ul>
  </div>
  <div
    use:ref
    class="subbox"
    style="flex-grow: 1; --pagex: {x}px; --pagey: {y}px;"
  >
    <h2 style="color: var(--lime);">GRAPHIC DESIGNERS</h2>
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
    padding: 2rem 2rem 2rem 2rem;
    text-align: center;
    border: 0.3rem solid rgba(255, 255, 255, 0.2);
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
    padding: 1rem 1rem 1rem 1rem;
  }

  .subbox:hover {
    border-radius: 1rem;
    background-origin: border-box;
    background-image: radial-gradient(
      circle at var(--pagex) var(--pagey),
      #b7ff003f,
      transparent 50%
    );
  }

  h2 {
    color: antiquewhite;
    font-family: Lato;
    text-align: center;
    font-size: 1.3rem;
  }
  a {
    color: antiquewhite;
    font-family: Lato;
    text-align: center;
    font-size: 3rem;
    text-decoration: none;
  }
  ul {
    color: antiquewhite;
    font-size: 1rem;
    line-height: 150%;
    font-family: Lato;
    list-style-type: none;
    text-decoration: none;
    padding: 0;
    margin: 0;
  }
</style>
