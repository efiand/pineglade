<script lang="ts">
	import Image from '$lib/components/Image.svelte';
	import { StatusCodes } from 'http-status-codes';
	import { page } from '$app/stores';

	export let isIndex = false;
</script>

<header class="container">
	<h1>
		<a href={isIndex ? null : '/'} aria-current={isIndex ? 'page' : null}>
			<Image
				filename="pineglade-logo.svg"
				width="100"
				height="100"
				alt="Логотип веб-студии «Сосновая Поляна»."
			/>

			<span>Веб-студия <em>«Сосновая Поляна»</em></span>
		</a>
	</h1>

	{#if $page.status === StatusCodes.NOT_FOUND}
		<p>
			Страница не найдена.

			<a href="mailto:dev@pineglade.ru">Связаться с разработчиком</a>.
		</p>
	{/if}
</header>

<style lang="scss">
	header {
		display: flex;
		flex-direction: column;
		gap: 60px;
		align-items: center;
		box-sizing: border-box;
		min-height: 100vh;
		padding-top: 60px;
		padding-bottom: 60px;
		text-align: center;
		color: $color-white;
		background-color: $color-bg;
	}

	h1 {
		margin: auto;
		font-weight: 400;
		font-size: 60px;
		line-height: 1.067;
		font-family: $font-playfair;
	}

	h1 a {
		display: flex;
		flex-direction: column;
		gap: 40px;
		align-items: center;
	}

	em {
		color: $color-brown;
	}
</style>
