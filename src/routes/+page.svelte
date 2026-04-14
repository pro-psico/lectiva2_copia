<script lang="ts">
	import { goto } from '$app/navigation';
	import { base } from '$app/paths';
	import { CharacterBrowser } from '$lib/features/character-browser';
	import type { PageData } from './$types';

	export let data: PageData;

	function updateFilters(filters: { query: string; status: string }) {
		const trimmed = filters.query.trim();
		const params = new URLSearchParams();

		if (trimmed) {
			params.set('q', trimmed);
		}

		if (filters.status) {
			params.set('status', filters.status);
		}

		const target = params.toString() ? `${base}/?${params.toString()}` : `${base}/`;
		goto(target, { replaceState: true, noScroll: true });
	}
</script>

<CharacterBrowser data={data} onFiltersChange={updateFilters} />
