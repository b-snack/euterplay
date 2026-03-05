<script lang="ts">
  import Searchbar from "$lib/Searchbar.svelte";

  let value = $state("");

  async function handleAction() {
    // array.forEach((element) => {});
  }
</script>

<Searchbar />

<div class="Sidebar">// recently listened songs & Queue</div>

<style>
  .Sidebar {
    justify-content: left;
  }
  ul {
    padding: 8px;
  }
</style>
