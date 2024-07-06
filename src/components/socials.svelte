<script>
	import Codeberg from "./codeberg.svelte";
	import Github from "./github.svelte";
	import Misskey from "./misskey.svelte";
	import Discord from "./discord.svelte";
	import Email from "./email.svelte";

	const tooltipText = {
		codeberg: "Visit Site",
		github: "Visit Site",
		misskey: "Visit Site",
		discord: "Copy To Clipboard",
		email: "Copy To Clipboard"
	};

  function visitSite(content) {
    window.open(content);
  };

  function copySocialToClipboard(content) {
    navigator.clipboard.writeText(content);
  };
</script>

<div class="noselect social-icons">
	<a href="https://codeberg.org/hpsaucii" target="_blank" class="icon-button" aria-label="Codeberg">
		<Codeberg />
		<span class="tooltiptext">{tooltipText.codeberg}</span>
	</a>
	<a href="https://github.com/hpsaucii" target="_blank" class="icon-button" aria-label="Github">
		<span class="tooltiptext">{tooltipText.github}</span>
		<Github />
	</a>
	<a href="https://transfem.social/@hpsaucii" target="_blank" class="icon-button" aria-label="transfem.social">
		<span class="tooltiptext">{tooltipText.misskey}</span>
		<Misskey />
	</a>
	<button on:click={() => copySocialToClipboard("hpsaucii")} class="icon-button" aria-label="Discord">
		<span class="tooltiptext">{tooltipText.discord}</span>
		<Discord />
	</button>
	<button on:click={() => copySocialToClipboard("me [AT] hpsaucii [DOT] dev")} class="icon-button" aria-label="Email">
		<span class="tooltiptext">{tooltipText.email}</span>
		<Email />
	</button>
</div>

<style>
	.social-icons {
		font-size: 3rem;
	}

	.icon-button {
	  background: none;
	  border: none;
	  padding: 0;
	  cursor: pointer;
	  display: inline-flex;
	  align-items: center;
	  justify-content: center;
	  width: 48px;
	  height: 48px;
	  margin: 0 8px;
	  position: relative;
	}

	.icon-button:focus {
	  outline: none;
	}

	.icon-button .tooltiptext {
	  font-size: 1rem;
	  visibility: hidden;
	  padding: 1rem 1rem;
	  background-color: var(--mantle);
	  color: var(--text);
	  text-align: center;
	  border-radius: 0.1em;
	  white-space: nowrap;
	  position: absolute;
	  z-index: 1;
	  bottom: 100%;
	  left: 50%;
	  transform: translateX(-50%);
	  margin-bottom: 5px;
	  transition-property: visibility;
	  transition-delay: 0s;
	}

	.icon-button .tooltiptext::after {
	  content: '';
	  position: absolute;
	  top: 100%;
	  left: 50%;
	  transform: translateX(-50%);
	  border-width: 5px;
	  border-style: solid;
	  border-color: var(--mantle) transparent transparent transparent;
	}

	.icon-button:hover .tooltiptext {
	  visibility: visible;
	  transition-delay: 0.3s;
	}
</style>
