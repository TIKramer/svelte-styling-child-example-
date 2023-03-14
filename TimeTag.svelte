<script lang="ts">
	import Time from 'carbon-icons-svelte/lib/Time.svelte';
	import Tag from '$lib/components/Tag/Tag.svelte';
	export let type: 'daily' | 'weekly' | 'monthly';
</script>

<Tag title={type} icon={Time} outline />
