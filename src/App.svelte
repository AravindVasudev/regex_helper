<script lang="ts">
  let expression = "";
  let example = "";
  let examples = 1;
  let valid = false;
</script>

<main>
<input
  type="text"
  bind:value={expression}
  class="expression"
  placeholder="Enter regex here..." />

  <br />

  {#each Array(examples) as _}
    <input
      bind:value={example}
      placeholder="Enter example here" />
      {#if example && example.match(expression)}👍{/if}
  {/each}
</main>

<style>
  .expression {
    display: block;
    width: 80%;
  }
</style>
