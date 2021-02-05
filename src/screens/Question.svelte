<script type="ts">
  import { createEventDispatcher } from "svelte";

  export let selection;
  const dispatch = createEventDispatcher();
</script>

<h1>{selection.question}</h1>

<button on:click={() => dispatch("restart")}>Another?</button>
