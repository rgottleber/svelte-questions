<script lang="ts">
  import { onMount } from "svelte";
  import Question from "./screens/Question.svelte";
  import Welcome from "./screens/Welcome.svelte";

  let state = "welcome";
  let selection;
  const start = async (e) => {
    const { question } = await load_question();
    selection = question;
    state = "questions";
  };

  const load_question = async () => {
    const res = await fetch(
      "https://random-question.herokuapp.com/api/questions/random"
    );
    const data = await res.json();
    return data;
  };
</script>

<main>
  {#if state === "welcome"}
    <Welcome on:select={start} />
  {:else if state === "questions"}
    <Question {selection} on:restart={() => (state = "welcome")} />
  {/if}
</main>

<style>
</style>
