<script lang="ts">
	export let title: string;
	export let icon: any = undefined;
	export let outline: boolean = false;
	$: capitalised = title.charAt(0).toUpperCase() + title.slice(1);
</script>
<div class="container" class:outline>
	{#if icon}
		<div class="iconContainer">
			<svelte:component this={icon} />
		</div>
	{/if}
	<span class="text">{capitalised}</span>
</div>
<style>
	.container {
		display: inline-flex;
		align-items: center;
		border-radius: 0.5em;
		font-size: 1em;
		line-height: 1em;
		padding: 0.1em 0.2em;
		background-color: var(--background-color);
		color: var(--color);
	}
	.outline {
		outline: 1px solid;
	}
	.iconContainer {
		display: flex;
		justify-content: center;
		align-items: center;
		padding-right: 5px;
	}

</style>
