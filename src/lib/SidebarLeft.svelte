<script lang="ts">
  import Searchbar from "$lib/Searchbar.svelte";

  let value = $state("");

  async function handleAction() {
    // array.forEach((element) => {});
  }
</script>

<Searchbar />

<div class="Sidebar">
  <h1>Your Library</h1>
  <button>Create</button>
  <button>Expand your Library</button>
  <div class="playlists">
    <li>
      <ul>//Insert Playlist Here</ul>
    </li>
  </div>
</div>

<style>
  .Sidebar {
    justify-content: left;
  }
  ul {
    padding: 8px;
  }
</style>
