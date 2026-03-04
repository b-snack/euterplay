<script lang="ts">
  import Searchbar from "$lib/Searchbar.svelte";

  let value = $state("");

  async function handleAction() {
    // your logic here
  }
</script>

<Searchbar />

<main>
  <h1>Title</h1>
</main>

<style>
  main {
    margin-top: 80px;
    padding: 2rem;
  }
</style>
