<script type="ts">
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();

  let selected = false;

  const select = () => {
    selected = true;
    dispatch("select");
  };
</script>

<div>
  <header><h1>Conversation Starters</h1></header>

  <p>Are you ready for a new conversation?</p>

  <button on:click={() => select()} disabled={selected}> Sure! </button>
</div>

<style>
  div {
    text-align: center;
  }
</style>
