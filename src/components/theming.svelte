<script>
  let selectedTheme;
  let selectedAccent;

	let themes = [
		"Latte",
		"Frappe",
		"Macchiato",
		"Mocha",
  ];

	let accents = [
		"Rosewater",
		"Flamingo",
		"Pink",
		"Mauve",
		"Red",
		"Maroon",
		"Peach",
		"Yellow",
		"Green",
		"Teal",
		"Sky",
		"Sapphire",
		"Blue",
		"Lavender"
	];

	function handleThemeChange() {
    document.documentElement.setAttribute('data-theme', selectedTheme.toLowerCase());
  };

  function handleAccentChange() {
    document.documentElement.style.setProperty('--accent', `var(--${selectedAccent.toLowerCase()})`);
  };
</script>

<label class="jsonly">
  Flavour:
  <select bind:value={selectedTheme} on:change={handleThemeChange} aria-label="Select Theme">
		{#each themes as theme}
			{#if theme == "Mocha"}
				<option value={theme} selected>{theme}</option>
			{:else}
			<option value={theme}>{theme}</option>
			{/if}
		{/each}
  </select>
</label>
<label class="jsonly">
  Accent Color:
  <select bind:value={selectedAccent} on:change={handleAccentChange} aria-label="Select Accent Color">
  	{#each accents as accent}
  		{#if accent == "Mauve"}
				<option value={accent} selected>{accent}</option>
			{:else}
			<option value={accent}>{accent}</option>
			{/if}
		{/each}
  </select>
</label>

<style>
	label {
		display: flex;
		align-items: center;
		justify-content: center;
		margin-bottom: 10px;
		width: 100%;
	}
	
	label select {
	    margin-left: 5px;
			min-width: 25px;
			width: auto;
	}
	
	select {
	  color: var(--text);
	  background-color: var(--mantle);
	  border: var(--crust);
	  padding: 0 1m 0 0;
	  margin: 0;
	  width: 10%;
	  font-family: inherit;
	  font-size: inherit;
	  cursor: inherit;
	  line-height: inherit;
	}
</style>
