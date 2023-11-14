<script>
  let inputArray = "";
  let trimmedInput = "";
  let arrayOfObjects = [
    {color: "red", type: "minivan", doorcount: "5", year: "2010"},
    {color: "green", type: "sedan", doorcount: "4", year: "2009"},
    {color: "blue", type: "truck", doorcount: "2", year: "2015"},
  ];

function addObject() {
    trimmedInput = inputArray.trim();
}

function handleInput(event) {
   inputArray = event.target.value;
}

    // Check if the input value is not empty before adding to the array
    if (trimmedInput !== "") {
      const newObject = { id: arrayOfObjects.length + 1, name: trimmedInput };

      // Use push method to add the new object to the array
      arrayOfObjects.push(newObject);

      // Clear the input after adding to the array
      inputArray = "";
    }
  </script>

<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>

<div>
  <h1>Array of Objects</h1>
  <ul>
    {#each arrayOfObjects as obj (obj.id)}
      <li>{obj.name}</li>
    {/each}
  </ul>

  <label for="text-input">Text input</label>: 
  <input type="text" id="text-input" bind:value={inputArray}>

  <button on:click={addObject}>Add Object</button>
</div>