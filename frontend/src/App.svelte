<script>
  import { running, registered } from "./store.js";
  import StartGame from "./StartGame.svelte";
  import Memory from "./Memory.svelte";
  import Players from "./Players.svelte";

  let game = { running: false };
  running.subscribe(val => (game.running = val));
</script>

<style>
  :global(body) {
    background: #7ec2c2;
  }
</style>

{#if game.running}
  <Memory />
{:else if $registered}
  <Players />
{:else}
  <StartGame />
{/if}
