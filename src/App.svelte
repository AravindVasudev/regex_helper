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

    border: 0.1em solid #DD4B1A;
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
    color: #FFEEDB;
    
    background-color: #DD4B1A;
  }

  #expression > input {
    width: 100%;
    box-sizing: border-box;
    flex: 1;

    font-family: 'Space Mono', monospace;
    font-weight: bold;
    font-size: 1em;

    padding-left: 0.5em;
    padding-right: 0.5em;
    border: 0;

    background-color: #FFEEDB;
  }

  #divider {
    height: 1em;
    width: 100%;
    flex: 0.25;

    background-color: #DD4B1A;
  }

  #example {
    width: 100%;
    box-sizing: border-box;
    flex: 10;

    background-color: #FFEEDB;
  }

  #expression > input:focus,
  #example:focus {
    outline: none;
  }
</style>
