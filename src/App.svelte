<script lang="ts">
  // Data-binded html elements.
  let backdropDiv;
  let highlightDiv;
  let exampleTextArea;

  // Data-binded values.
  let expression = "";
  let example = "";

  // Add highlights within the text area.
  function highlight() {
    if (!expression) {
      return;
    }

    let highlight = example
      .replace(/\n$/g, "\n\n")
      .replace(new RegExp(expression, "g"), "<mark>$&</mark>");

    highlightDiv.innerHTML = highlight;
  }

  // Handles scrolling highlights within the text area.
  function scroll() {
    backdropDiv.scrollTop = exampleTextArea.scrollTop;
    backdropDiv.scrollLeft = exampleTextArea.scrollLeft;
  }
</script>

<main>
  <div id="expression">
    <label for="expression">Expression</label>
    <input
      type="text"
      bind:value={expression}
      placeholder="Enter regex here..."
    />
  </div>
  <div id="divider" />
  <div id="example">
    <div class="backdrop" bind:this={backdropDiv}>
      <div class="highlights" bind:this={highlightDiv}>
        <!-- This section would be populated with highlighted text. -->
      </div>
    </div>
    <textarea
      name="example"
      bind:this={exampleTextArea}
      bind:value={example}
      on:input={highlight}
      on:scroll={scroll}
    />
  </div>
</main>

<style>
  main {
    /* Center the frame. */
    height: 80vh;
    width: 80vw;

    margin: auto;
    display: flex;
    flex-direction: column;

    border: 0.1em solid #dd4b1a;
  }

  #expression > label {
    /* label is set to be a full length block. */
    display: block;
    width: 100%;
    flex: 1;

    padding: 0.25em;
    padding-left: 0.5em;

    font-weight: bold;
    color: #ffeedb;

    background-color: #dd4b1a;
  }

  #expression > input {
    width: 100%;
    flex: 1;

    font-weight: bold;
    font-size: 1em;

    padding-left: 0.5em;
    padding-right: 0.5em;
    border: 0;

    background-color: #ffeedb;
  }

  #divider {
    height: 1em;
    width: 100%;
    flex: 0.25;

    background-color: #dd4b1a;
  }

  #example {
    width: 100%;
    flex: 10;

    position: relative;
  }

  #example > textarea {
    display: block;
    width: 100%;
    height: 100%;

    border-radius: 0;
    padding-left: 0.5em;
    padding-right: 0.5em;

    position: absolute;
    z-index: 2;
    resize: none;
    overflow: auto;

    background-color: transparent;
  }

  #expression > input:focus,
  #example > textarea:focus {
    outline: none;
  }

  #example > .backdrop {
    width: 100%;
    height: 100%;

    position: absolute;
    padding-left: 0.5em;
    padding-right: 0.5em;

    overflow: auto;
    pointer-events: none;

    background-color: #ffeedb;
  }

  #example > .backdrop > .highlights {
    white-space: pre-wrap;
    word-wrap: break-word;

    color: transparent;
  }

  :global(mark) {
    color: transparent;

    border-radius: 3px;
    background-color: #73c2be;
  }
</style>
