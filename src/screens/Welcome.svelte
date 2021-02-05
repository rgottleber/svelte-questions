<script type="ts">
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();

  let selected = false;

  const select = () => {
    selected = true;
    dispatch("select");
  };
</script>

<header><h1>What to Ask?</h1></header>

<p>Are you ready for a new questions?</p>

<div>
  <button on:click={() => select()} disabled={selected}> New Question </button>
</div>
