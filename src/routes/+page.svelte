<script lang="ts">
  import Searchbar from "$lib/Searchbar.svelte";
  import Sidebar from "$lib/Sidebar.svelte";

  let value = $state("");

  async function handleAction() {
    // your logic here
  }
</script>

<Searchbar />

<main></main>

<style>
  main {
  }
</style>
