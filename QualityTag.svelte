<script lang="ts">
	import CheckmarkOutline from 'carbon-icons-svelte/lib/CheckmarkOutline.svelte';
	import WarningAlt from 'carbon-icons-svelte/lib/WarningAlt.svelte';
	import Error from 'carbon-icons-svelte/lib/Error.svelte';
	import Tag from '$lib/components/Tag/Tag.svelte';
	export let state: 'fresh' | 'old' | 'expired';
  
	let color: string;
	let backgroundColor: string;
	$: {
		if (state === 'fresh') {
			color = 'white';
			backgroundColor = 'green';
		} else if (state === 'old') {
			color = 'white';
			backgroundColor = 'orange';
		} else if (state === 'expired') {
			color = 'white';
			backgroundColor = 'red';
		}
	}
	function getIcon(type: string) {
		let icon = CheckmarkOutline;
		if (type === 'fresh') {
			icon = CheckmarkOutline;
		} else if (type === 'old') {
			icon = WarningAlt;
		} else {
			icon = Error;
		}
		return icon;
	}
	$: Icon = getIcon(state);
</script>

<Tag title={state} icon={Icon} --background-color={backgroundColor} --color={color} />
