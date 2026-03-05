<script lang="ts">
  import Searchbar from "$lib/Searchbar.svelte";

  let value = $state("");

  async function handleAction() {
    // your logic here
  }
</script>

<Searchbar />

<div class="Sidebar">
  <h1>Your Library</h1>
</div>

<style>
  .Sidebar {
    justify-content: left;
  }
</style>
