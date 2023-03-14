<script lang="ts">
	import Apple from 'carbon-icons-svelte/lib/Apple.svelte';
	import Strawberry from 'carbon-icons-svelte/lib/Strawberry.svelte';
	import Tag from '$lib/components/Tag/Tag.svelte';
	export let type = "apple" || "strawberry";
	let color: string;
	let backgroundColor: string;
	$: {
		if (type === "apple") {
			color = 'white';
			backgroundColor = 'green';
		} else if (type === "strawberry") {
			color = 'white';
			backgroundColor = 'red';
		}
	}

	function getIcon(type: string) {
		let icon = Apple;
		if (type === "apple") {
			icon = Apple;
		} else if (type === "strawberry") {
			icon = Strawberry;
		} 
		return icon;
	}
	$: Icon = getIcon(type);
</script>

<Tag title={type} icon={Icon} --background-color={backgroundColor} --color={color} />
