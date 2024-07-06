<script>
    let selectedTheme = "mocha";
    let selectedAccent = "mauve";

    let themes = [
        { id: 1, value: "latte", text: "Latte" },
        { id: 2, value: "frappe", text: "Frappe" },
        { id: 3, value: "macchiato", text: "Macchiato" },
        { id: 4, value: "mocha", text: "Mocha" }
    ];

    function handleThemeChange() {
        console.log(`Changing theme to: ${selectedTheme}`);
    document.documentElement.setAttribute('theme', selectedTheme);
  };

    function handleAccentChange() {
    document.documentElement.style.setProperty('--accent', `var(--${selectedAccent})`);
  };

</script>

<label>
  Flavour:
  <select bind:value={selectedTheme} on:change={handleThemeChange} aria-label="Select Theme">
      {#each themes as theme}
            <option value={theme.value}>
                {theme.text}
            </option>
        {/each}
  </select>
</label>
<label>
  Accent Color:
  <select bind:value={selectedAccent} on:change={handleAccentChange} aria-label="Select Accent Color">
    <option value="rosewater">Rosewater</option>
    <option value="flamingo">Flamingo</option>
    <option value="pink">Pink</option>
    <option value="mauve">Mauve</option>
    <option value="red">Red</option>
    <option value="maroon">Maroon</option>
    <option value="peach">Peach</option>
    <option value="yellow">Yellow</option>
    <option value="green">Green</option>
    <option value="teal">Teal</option>
    <option value="sky">Sky</option>
    <option value="sapphire">Sapphire</option>
    <option value="blue">Blue</option>
    <option value="lavender">Lavender</option>
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
