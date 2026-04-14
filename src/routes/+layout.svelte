<svelte:head>
	<title>Prueba Lectiva</title>
	<meta
		name="description"
		content="Base SvelteKit con arquitectura feature-first/domain-first para integrar Rick and Morty."
	/>
</svelte:head>

<div class="app-shell">
	<slot />
</div>

<style>
	:global(html) {
		color-scheme: dark;
	}

	:global(body) {
		--color-bg: #101012;
		--color-bg-deep: #09090b;
		--color-surface: #1b171a;
		--color-surface-muted: #241d21;
		--color-text: #f8f3f4;
		--color-text-muted: #cdbec1;
		--color-text-soft: #a9959a;
		--color-border: #3a2d32;
		--color-accent: #ff6f78;
		--color-accent-contrast: #17090b;
		--color-accent-soft: rgba(255, 111, 120, 0.16);
		--color-focus: #ff9da3;
		--color-error: #ffb3b8;
		--shadow-elevated: 0 18px 42px rgba(0, 0, 0, 0.34);
		margin: 0;
		font-family:
			Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
		background:
			radial-gradient(circle at top left, rgba(255, 111, 120, 0.2), transparent 34rem),
			linear-gradient(180deg, var(--color-bg) 0%, var(--color-bg-deep) 100%);
		color: var(--color-text);
		min-height: 100vh;
	}

	.app-shell {
		min-height: 100vh;
	}
</style>
