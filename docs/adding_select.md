## 🪔 Adding Select2

Install library

```bash
npm i svelte-select@latest
```

Example with static data

```html
<script>
	import Select from 'svelte-select';
	
// 	Select
	let stateVal = undefined;
	const stateItem = [
    { value: 'AL', label: 'Alabama' },
    { value: 'AK', label: 'Alaska' },
    { value: 'CA', label: 'California' },
    { value: 'DE', label: 'Delaware' },
    { value: 'TN', label: 'Tennessee' },
    { value: 'TX', label: 'Texas' },
    { value: 'WA', label: 'Washington' },
  ];
	function stateHandle(event) {
		stateVal = event.detail;
	}
	
// 	Select Multi Item
	let stateMultiVal = undefined;
	const stateMultiItem = [
    { value: 'ED', label: 'England' },
    { value: 'NI', label: 'Northern Ireland' },
  ];
	function stateMultiHandle(event) {
		stateMultiVal = event.detail;
	}
	
// 	Checkbox
	let selectedCheckbox = [];
  let question = [
    { text: "Answer A", value: true },
    { text: "Answer B", value: false },
    { text: "Answer C", value: false },
    { text: "Answer D", value: true }
  ];
	
// 	Radio Input
	let radioInput = [];
	let country = [
		'USA',
		'UK',
	]
	
// 	File Input
	let files, fileInput;
	
	function resetValue() {
		stateVal = undefined;
		stateMultiVal = undefined;
	}
	
</script>

<h1>Form reset example</h1>

<form>
	<label for="title_id">Title :</label>
	<input type="text" id="title" placeholder="title..." class="form-control">
	<hr />
	
	<label for="question_id">Question :</label>
  <ul>
    {#each question as { value, text } (text)}
      <li>
        <label>
          <input type="checkbox" value={text} bind:group={selectedCheckbox} />
          <span>{text}</span>
        </label>
      </li>
    {/each}
  </ul>
	<hr />
	
	<label for="title_id">Country :</label>
	{#each country as value}
	<label><input type="radio" {value} bind:group={radioInput}> {value}</label>
	{/each}
	<hr />
	
	<label for="state">State</label>
	<Select value={stateVal} items={stateItem} on:select={stateHandle} isClearable={true} noOptionsMessage="No Data"></Select>
	<hr />
	
	<label for="state">State</label>
	<Select value={stateMultiVal} items={stateMultiItem} on:select={stateMultiHandle} isMulti={true} isClearable={true} noOptionsMessage="No Data"></Select>
	<hr />
	
	<label for="state">First choose a file.</label>
	<input type="file" bind:files bind:this={fileInput}>
	<hr />
	
	<button type="reset" on:click={resetValue}>Reset</button>
</form>


<style>
	form {
/* 		max-width: 400px; */
		background: #f4f4f4;
		padding: 20px;
		border-radius: 4px;
	}
	
	label {
		margin: 0 0 10px;
	}
	
	hr {
		border: 2px solid grey;
		border-radius: 5px;
	}
	
	h1 {
		text-align: center
	}
	
	button {
		margin: 10px 0;
	}
</style>
```
