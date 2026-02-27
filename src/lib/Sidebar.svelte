<script lang="ts">
  let playlists = $state(["Liked Songs"]);
</script>

<aside class="Sidebar">
  <h3>Playlists</h3>
  <ul class="playlist-list">
    {#each playlists as playlist}
      <li>{playlists}</li>
    {/each}
  </ul>
</aside>

<style>
  .Sidebar {
    height: 100%;
    background-color: #000000;
    padding: 20px;
    overflow-y: auto;
  }

  .playlist-list {
    list-style: none;
    padding: 0;
    margin: 0;
  }

  h3 {
    margin-bottom: 20px;
    font-size: 1.2em;
    margin-top: 0;
    color: #ffffff;
  }

  .playlist-list li {
    padding: 12px 16px;
    color: #b3b3b3;
    cursor: pointer;
    border-radius: 4px;
    transition: all 0.2s;
  }

  .playlist-list li:hover {
    background-color: #282828;
    color: #ffffff;
  }
</style>
