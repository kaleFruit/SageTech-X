<script>
    import Archive from "../archiveTemplate.svelte";

    const writers = [
        "Kevin Peng",
        "Oneal Wang",
        "Katherine Robertson",
        "Nicole Ma",
        "Jacob Lynn",
        "Derek Zuo",
        "Julia Wen",
        "Melody Yu",
        "Basim Cheema-Sabir",
        "Alen Zhang",
        "Kai Patragnoni",
        "Kevin Hu",
        "Harriet Lai",
        "Justin Kline",
        "Bruce Li",
        "Arshaun Oshideri",
        "Minki Shin",
        "Ridwan Simjee",
        "Anton Nguyen",
        "Nic Eimani",
        "Keyon Sabahi",
        "Nico Luo",
    ];
    const graphics = [
        "Marcus Yoo",
        "Jennifer Huang",
        "Katherine Robertson",
        "Danny Al-Ali",
        "Kevin Peng",
        "Minki Shin",
    ];
    const editors = [
        "Phoebe Pan",
        "Marcus Yoo",
        "Nico Luo",
        "Keyon Sabahi",
        "Peter Huang",
    ];
    const editorInChiefs = ["Kevin Peng", "Katherine Robertson", "Minki Shin"];
</script>

<div style="display: flex; justify-content: center; gap: 2rem;">
    <div class="names">
        <h4 class="header">Writers</h4>
        {#each writers as person}
            <p class="writer name">{person}</p>
        {/each}
    </div>
    <div class="names">
        <h4 class="header">Graphics Designers</h4>
        {#each graphics as person}
            <p class="graphic name">{person}</p>
        {/each}
    </div>
    <div class="names">
        <h4 class="header">Editors</h4>
        {#each editors as person}
            <p class="editor name">{person}</p>
        {/each}
    </div>
    <div class="names">
        <h4 class="header">Editor-in-Chiefs</h4>
        {#each editorInChiefs as person}
            <p class="editorInChief name">{person}</p>
        {/each}
    </div>
</div>

<style>
    .names {
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        align-items: center;
        gap: 0rem;
    }
    .name {
        margin: 0;
    }
    .writer {
        color: var(--primary-color);
    }
    .graphic {
        color: var(--primary-accent);
    }
    .editor {
        color: var(--beige);
    }
    .editorInChief {
        color: var(--darker-accent);
    }
    .header {
        text-align: center;
        margin-bottom: 2rem;
        max-width: 10rem;
        height: 6rem;
        font-size: 2rem;
    }
</style>
