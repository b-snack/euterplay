<script lang="ts">
  import { Search } from "lucide-svelte";

  let value = $state("");
  let searchQuery = $state("");

  async function handleSearchSubmit(event: Event) {
    const query = (event.target as HTMLInputElement).value;
    searchQuery = query;
    // Logic will be added
  }
</script>

<div class="top-bar">
  <input
    type="search"
    placeholder="Enter song title / lyric..."
    bind:value={searchQuery}
    oninput={handleSearchSubmit}
  />
</div>

<style>
  .top-bar {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 0.5rem, 1rem;
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    width: 100%;
    height: 64px;
    z-index: 1000;
    background-color: black;
  }

  input {
    width: 100%;
    max-width: 400px;
    height: 40px;
    font-size: 14px;
    padding: 0 2.5rem 0 1rem;
    border-radius: 500px;
    border: none;
    background-color: #242424;
    color: #ffffff;
    outline: none;
  }
</style>
