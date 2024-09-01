<script>
    import { useMousePosition } from "@svelteuidev/composables";
    const [position, ref] = useMousePosition();
    $: ({ x, y } = $position);
</script>

<div
    style="
    display: flex; 
    flex-wrap: wrap;
    justify-content: space-between;
    gap: 2rem;
    "
>
    <div
        use:ref
        class="role"
        style="--color:var(--primary-color); flex-grow: 1; --pagex: {x}px; --pagey: {y}px;"
    >
        <h>EDITORS</h>
        <div class="cards">
            <div class="infoCard">
                <h2>Kevin Peng</h2>
                <p>Years: 2023-Present</p>
                <p>Grade: Senior</p>
            </div>
        </div>
    </div>
    <div
        use:ref
        class="role"
        style="--color: var(--primary-color); flex-grow: 1;  --pagex: {x}px; --pagey: {y}px;"
    >
        <h>GRAPHIC DESIGNERS</h>
        <div class="cards">
            <div class="infoCard">
                <h2>Kevin Peng</h2>
                <p>Years: 2023-Present</p>
                <p>Grade: Senior</p>
            </div>
            <div class="infoCard">
                <h2>Danny Al-Ali</h2>
                <p>Years: 2023-Present</p>
                <p>Grade: Junior</p>
            </div>
        </div>
    </div>
    <div
        use:ref
        class="role"
        style="--color: var(--primary-color); width: 100%; --pagex: {x}px; --pagey: {y}px;"
    >
        <h>WRITERS</h>
        <div class="cards">
            <div class="infoCard">
                <h2>Kevin Peng</h2>
                <p>Years: 2023-Present</p>
                <p>Grade: Junior</p>
            </div>
            <div class="infoCard">
                <h2>Oneal Wang</h2>
                <p>Years: 2022-Present</p>
                <p>Grade: Junior</p>
            </div>
            <div class="infoCard">
                <h2>Jacob Lynn</h2>
                <p>Years: 2022-Present</p>
                <p>Grade: Junior</p>
            </div>
            <div class="infoCard">
                <h2>Derek Zuo</h2>
                <p>Years: 2022-Present</p>
                <p>Grade: Junior</p>
            </div>
            <div class="infoCard">
                <h2>Melody Yu</h2>
                <p>Years: 2022-Present</p>
                <p>Grade: Junior</p>
            </div>
            <div class="infoCard">
                <h2>Alen Zhang</h2>
                <p>Years: 2022-Present</p>
                <p>Grade: Junior</p>
            </div>
            <div class="infoCard">
                <h2>Harriet Lai</h2>
                <p>Years: 2023-Present</p>
                <p>Grade: Junior</p>
            </div>
            <div class="infoCard">
                <h2>Justin Kline</h2>
                <p>Years: 2023-Present</p>
                <p>Grade: Sophomore</p>
            </div>
            <div class="infoCard">
                <h2>Bruce Li</h2>
                <p>Years: 2023-Present</p>
                <p>Grade: Sophomore</p>
            </div>
            <div class="infoCard">
                <h2>Arshaun Oshideri</h2>
                <p>Years: 2023-Present</p>
                <p>Grade: Sophomore</p>
            </div>
        </div>
    </div>
</div>

<style>
    .infoCard {
        border: 1px solid rgba(215, 218, 250, 0.343);
        border-radius: 1rem;
        padding: 0.5rem;
        background-color: #1f1f1f;
    }
    .role {
        border: 1px solid rgba(255, 255, 255, 0.1);
        background: #1212127a;
        border-radius: 1rem;
        padding: 1rem;
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        align-content: center;
        flex-direction: column;
    }

    .role:hover {
        border-radius: 1rem;
        background-origin: border-box;
        background-image: radial-gradient(
            circle at var(--pagex) var(--pagey),
            rgba(var(--darker-accent-rgb), 0.2),
            transparent 50%
        );
    }
    .role h {
        color: var(--color, #ddd);
        font-family: "Inter";
        text-align: center;
        font-size: 1.3rem;
    }

    .cards {
        padding: 1rem;
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        align-content: center;
        gap: 1rem;
    }
    .infoCard h2 {
        color: antiquewhite;
        font-family: "Inter";
        font-size: 1rem;
        text-align: center;
    }
    .infoCard p {
        color: antiquewhite;
        font-family: "Inter";
        font-size: 1rem;
        text-align: center;
    }
</style>
