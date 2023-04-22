<script lang="ts">
	import { page } from '$app/stores';

	let isIndex: boolean;

	$: isIndex = $page.url.pathname === '/';
</script>

<header>
	<h1>
		<a href={isIndex ? null : '/'} aria-current={isIndex ? 'page' : null}>
			Веб-студия «Сосновая Поляна»
		</a>
	</h1>
</header>

<style lang="scss">
	header {
		text-align: center;
	}
</style>
