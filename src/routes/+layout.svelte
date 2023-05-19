<script lang="ts">
	import '$lib/styles/app.scss';
	import { DOMAIN, PROJECT } from '$lib/utils/constants';
	import Footer from '$lib/components/Footer.svelte';
	import Header from '$lib/components/Header.svelte';
	import { page } from '$app/stores';

	let isIndex: boolean;
	let title: string;
	let url: string;

	$: isIndex = $page.url.pathname === '/';
	$: title = `${PROJECT}: ${$page.data.title}`;
	$: url = `${DOMAIN}${$page.url.pathname}`;
</script>

<svelte:head>
	<title>{title}</title>
	<meta name="description" content="Страница «{$page.data.title}» сайта «${PROJECT}»." />
	<link rel="canonical" href={url} />
	<meta property="og:site_name" content={PROJECT} />
	<meta property="og:title" content={title} />
	<meta property="og:url" content={url} />
</svelte:head>

<Header {isIndex} />

<main>
	<slot />
</main>

{#if isIndex}
	<Footer />
{/if}
