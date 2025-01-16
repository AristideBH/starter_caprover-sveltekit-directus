<script lang="ts">
	import { MediaQuery } from 'svelte/reactivity';
	import { page } from '$app/state';
	import DesktopNav from './desktop/DesktopNav.svelte';
	import MobileNav from './mobile/MobileNav.svelte';

	const large = new MediaQuery('min-width: 620px');
	const { headerNav: menu } = page.data;
</script>

<nav class="pointer-events-auto flex flex-row items-center gap-6 xl:gap-10">
	{#if large.current}
		<DesktopNav {menu} />
	{:else}
		<MobileNav {menu} />
	{/if}
</nav>
