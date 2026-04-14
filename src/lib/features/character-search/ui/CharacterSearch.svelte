<script lang="ts">
	export let query: string = '';
	export let status: string = '';
	export let onFiltersChange: (filters: { query: string; status: string }) => void;

	function updateFilters() {
		onFiltersChange({ query, status });
	}
</script>

<div class="filters">
	<label class="search">
		<span>Buscar personaje</span>
		<input
			type="search"
			placeholder="Rick, Morty, Summer..."
			bind:value={query}
			on:input={updateFilters}
		/>
	</label>

	<label class="status">
		<span>Estado</span>
		<select
			bind:value={status}
			on:change={updateFilters}
		>
			<option value="">Todos</option>
			<option value="alive">Vivos</option>
			<option value="dead">Muertos</option>
			<option value="unknown">Estado desconocido</option>
		</select>
	</label>
</div>

<style>
	.filters {
		display: grid;
		grid-template-columns: minmax(0, 1fr) minmax(180px, 240px);
		gap: 1rem;
		align-items: end;
	}

	.search {
		display: grid;
		gap: 0.55rem;
	}

	.status {
		display: grid;
		gap: 0.55rem;
	}

	.search span,
	.status span {
		font-size: 0.92rem;
		color: var(--color-text-muted);
	}

	input,
	select {
		width: 100%;
		box-sizing: border-box;
		border: 1px solid var(--color-border);
		background: var(--color-surface);
		color: var(--color-text);
		padding: 0.95rem 1rem;
		border-radius: 8px;
		outline: none;
	}

	input::placeholder {
		color: var(--color-text-soft);
	}

	input:focus,
	select:focus {
		border-color: var(--color-focus);
		box-shadow: 0 0 0 4px var(--color-accent-soft);
	}

	@media (max-width: 640px) {
		.filters {
			grid-template-columns: 1fr;
		}
	}
</style>
