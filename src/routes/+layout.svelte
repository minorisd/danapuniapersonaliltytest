<script lang="ts">
	import favicon from "$lib/assets/favicon.svg";
	import "carbon-components-svelte/css/all.css";

	import {
		Content,
		Header,
		HeaderAction,
		HeaderPanelDivider,
		HeaderPanelLink,
		HeaderPanelLinks,
		HeaderUtilities,
		SkipToContent, Theme,
	} from "carbon-components-svelte";

	import SettingsAdjust from "carbon-icons-svelte/lib/SettingsAdjust.svelte";

	let { children } = $props();

	let isOpen = $state(false);
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<Theme
		theme="white"
/>

<Header
		companyName="Yayasan Dana Punia"
		platformName="Personality test"
>
	<svelte:fragment slot="skipToContent">
		<SkipToContent />
	</svelte:fragment>

	<HeaderUtilities>
		<HeaderAction
				bind:isOpen
				icon={SettingsAdjust}
				iconDescription="Settings"
				text="Settings"
				tooltipAlignment="start"
				on:open={() => isOpen = true}
				on:close={() => isOpen = false}
		>
			<HeaderPanelLinks>
				<HeaderPanelDivider>Settings</HeaderPanelDivider>
				<HeaderPanelLink>language</HeaderPanelLink>
				<HeaderPanelLink>previous results</HeaderPanelLink>
			</HeaderPanelLinks>
		</HeaderAction>
	</HeaderUtilities>
</Header>

<Content>
	{@render children()}
</Content>