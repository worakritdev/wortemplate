<script context="module">
</script>

<script>
  import PokeDex from "./PokeDex.svelte";

  import Fuse from "fuse.js";
  import { onMount } from "svelte";
  let q = "";
  let result = [];
  let fuse;
  onMount(async () => {
    const res = await fetch("https://pokeapi.co/api/v2/pokemon?limit=100");

    const { results } = await res.json();
    fuse = new Fuse(results, {
      keys: ["name", "content", "description"],
      findAllMatches: true,
      includeScore: true,
    });
  });

  function searchTerm() {
    result = fuse.search(q);

    console.log(fuse, q, fuse.search(q));
  }
</script>

<div class="container">
  <input
    type="search"
    bind:value={q}
    on:change={searchTerm}
    class="bg-indigo-300"
  />
  <section>
    {#each result as { item: { name, url } }}
      <p>
        <PokeDex {name} {url} />
      </p>
    {/each}
  </section>
</div>

<!-- markup (zero or more items) goes here -->
<style>
  /* your styles go here */
</style>
