<script>
	import { base } from '$app/paths'
	import { page } from '$app/stores'
</script>

<!-- This page handles any error encountered by the site. -->

<div class="mx-auto max-w-page">
	<h1 class="text-4xl font-bold mt-8">Woops!</h1>
	<p class="py-4 text-xl">
		{#if $page.status === 404}
			We checked everywhere, but the thing you wanted was NotFound. Sorry!
		{:else}An unexpected error occurred.{/if}
	</p>
</div>
