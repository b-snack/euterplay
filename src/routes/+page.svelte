<script lang="ts">
  import { invoke } from "@tauri-apps/api/core";
  import Sidebar from "$lib/Sidebar.svelte";
  import "../app.css";

  let name = $state("");
  let greetMsg = $state("");

  async function greet(event: Event) {
    event.preventDefault();
    // Learn more about Tauri commands at https://tauri.app/develop/calling-rust/
    greetMsg = await invoke("greet", { name });
  }

  let results = [];

  // function handleInput(event) {
  //   const query = event.target.value;
  //   results = filterData(query);
  // }

  // function openPlaylist() {}
</script>

<slot />
<!-- Search bar -->

<div class="row-top">
  <input
    type="search"
    id="search-query"
    placeholder="Enter a song title / lyric..."
    bind:value={name}
  />
</div>

<!-- main site -->
<div class="container">
  <div class="sidebar-wrapper">
    <Sidebar />
  </div>

  <div class="main">
    <div class="content">
      <p>Search results appear here</p>
    </div>
  </div>

  <div class="right-panel">
    <p>Friend activity/notifs/queue, etc.</p>
  </div>
</div>

<style>
  :root {
    font-family: Inter, Avenir, Helvetica, Arial, sans-serif;
    font-size: 16px;
    line-height: 24px;
    font-weight: 400;

    color: #0f0f0f;
    background-color: #f6f6f6;

    font-synthesis: none;
    text-rendering: optimizeLegibility;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    -webkit-text-size-adjust: 100%;
  }

  .container {
    padding-top: 10px;
    /* display: flex;
    flex-direction: column;
    justify-content: center;
    text-align: center; */
    display: grid;
    grid-template-columns: 1fr 3fr 1fr;
    grid-template-rows: 100px auto;
    gap: 5px;
  }

  .sidebar-wrapper {
    margin-left: 8px;
    margin-right: 8px;
    margin-top: 8px;
    grid-column: 1;
    position: sticky;
    top: 0;
    height: 100vh;
    overflow-y: auto;
  }

  .row {
    padding-top: 0px;
    padding-bottom: 0px;
    display: flex;
    justify-content: center;
  }

  .row-top {
    top: 0;
    left: 0;
    width: 100%;
    padding: 5px;
    display: flex;
    justify-content: center;
    /* background-color: #5ccdaf; */
    z-index: 1000;
  }

  input,
  button {
    border-radius: 8px;
    border: 1px solid transparent;
    padding: 0.6em 1.2em;
    font-size: 1em;
    font-weight: 500;
    font-family: inherit;
    color: #0f0f0f;
    background-color: #ffffff;
    transition: border-color 0.25s;
    box-shadow: 0 2px 2px rgba(0, 0, 0, 0.2);
  }

  button {
    cursor: pointer;
  }

  button:hover {
    border-color: #396cd8;
  }
  button:active {
    border-color: #396cd8;
    background-color: #e8e8e8;
  }

  input,
  button {
    outline: none;
  }

  #search-query {
    margin-right: 5px;
  }

  .top {
    height: 60px;
    display: flex;
    flex-direction: columns;
    justify-content: center;
    align-items: center;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    z-index: 1000;
  }

  @media (prefers-color-scheme: dark) {
    :root {
      color: #f6f6f6;
      background-color: #2f2f2f;
    }

    input,
    button {
      color: #ffffff;
      background-color: #0f0f0f98;
    }
    button:active {
      background-color: #0f0f0f69;
    }
  }
</style>
