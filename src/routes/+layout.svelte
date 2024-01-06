<script>
	import Header from './components/Header.svelte';
	import Footer from './components/Footer.svelte';
	import Button from './components/Button.svelte';
	import ImageOutput from './components/ImageOutput.svelte';
	import './styles.css';
</script>

<div class="app">
	<Header />

	<main>
		<slot />
		<ImageOutput/>
		<Button/>
	</main>

	<Footer/>
</div>

<style>
	.app {
		margin: 0 auto;
		width: 800px;
		max-width: 800px;
	}

	/* @media (min-width: 480px) {
		footer {
			padding: 12px 0;
		}
	} */
</style>
