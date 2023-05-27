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

		&::before {
			content: '';
			position: absolute;
			top: 0;
			right: 0;
			left: 0;
			height: 100%;
			min-height: 100vh; // For mobile floating address bar
			background-image: url('/img/background.webp');
			background-position: 0 50%;
			background-size: cover;
			opacity: 0.075;
			filter: grayscale(1);
		}
	}

	h1 {
		position: relative;
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

	p {
		position: relative;
	}

	em {
		color: $color-brown;
	}
</style>
