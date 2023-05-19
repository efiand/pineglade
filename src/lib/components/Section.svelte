<script lang="ts">
	export let theme: 'white' | 'gray' | 'black' = 'white';
</script>

<section class="container {theme}">
	<slot />
</section>

<style lang="scss">
	section {
		padding-top: 75px;
		padding-bottom: 75px;
	}

	:global(h2) {
		margin: 0 0 45px;
		font-weight: 700;
		font-size: 40px;
		line-height: 1.125;
		font-family: $font-montserrat;
		letter-spacing: -2px;
		text-align: center;
		color: $color-title;
	}

	:global(b) {
		display: block;
		margin: 0 0 21px;
		font-size: 25px;
		line-height: 1.2;
		font-family: $font-montserrat;
		letter-spacing: -1px;
		color: $color-title;
	}

	:global(b em) {
		color: $color-brown;
	}

	:global(li:last-child b:last-child) {
		margin: 0;
	}

	:global(ul) {
		margin: 0;
		padding: 0;
		list-style: none;
	}

	:global(ul:not(.grid) > li + li) {
		margin-top: 60px;
	}

	:global(li),
	:global(p) {
		line-height: 2;
	}

	:global(dt) {
		margin: 0 0 10px;
		font-size: 24px;
		line-height: 1.2;
		font-family: $font-playfair;
		color: $color-title;
	}

	:global(dd) {
		margin-left: 1em;
	}

	.black {
		color: $color-white;
		background-color: $color-bg;

		:global(h2),
		:global(h2 em),
		:global(b) {
			color: inherit;
		}
	}

	.gray {
		background-color: $color-bg-light;

		:global(h2 em) {
			color: $color-brown;
		}
	}
</style>
