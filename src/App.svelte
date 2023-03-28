<script lang="ts">
  let expression = "";
  let examples = [""];
</script>

<main>
<div id="expression">
  <label for="expression">Expression</label>
  <input type="text" bind:value={expression} placeholder="Enter regex here..." />
</div>
<div id="divider"></div>
<textarea name="example" id="example" cols="30" rows="10"></textarea>
</main>

<style>
  main {
    /* Center the frame. */
    height: 100vh;
    width: 80%;
    box-sizing: border-box;

    margin: auto;
    display: flex;
    flex-direction: column;

    border: 0.1em solid #102E4A;
  }

  #expression > label {
    /* label is set to be a full length block. */
    display: block;
    box-sizing: border-box;
    width: 100%;

    flex: 1;

    padding: 0.25em;
    padding-left: 0.5em;

    font-family: 'Space Mono', monospace;
    font-weight: bold;
    font-size: 1em;
    
    background-color: #33A1FD;
    border: 0.1em solid #102E4A;
  }

  #expression > input {
    display: block;
    width: 100%;
    box-sizing: border-box;

    flex: 1;

    font-family: 'Space Mono', monospace;
    font-weight: bold;
    font-size: 1em;

    padding-left: 0.5em;
    padding-right: 0.5em;
    border: 0;
  }

  #divider {
    height: 1em;
    width: 100%;

    flex: 0.25;

    background-color: #102E4A;
  }

  #example {
    min-height: 70%;
    width: 100%;
    box-sizing: border-box;

    flex: 10;
  }

  #expression > input:focus,
  #example:focus {
    outline: none;
  }
</style>
