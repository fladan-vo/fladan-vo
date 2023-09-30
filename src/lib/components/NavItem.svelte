<script>
	import { currentPage, isMenuOpen } from '$lib/assets/js/store';
	import { base } from '$app/paths';
	export let href;

	$: isCurrentPage = $currentPage.startsWith(href);

	const maybeCloseMenu = () => {
		if (href != $currentPage) {
			isMenuOpen.set(false);
		}
	};
</script>

<li>
	<a
		href="{base}/{href}"
		on:click={maybeCloseMenu}
		class:active={isCurrentPage}
		aria-current={isCurrentPage ? 'page' : false}>
		<slot />
	</a>
</li>
