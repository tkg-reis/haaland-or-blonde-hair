<script>
	import Haaland01 from "../lib/images/haaland01.webp"
	import Haaland02 from "../lib/images/haaland02.webp"
	import Haaland03 from "../lib/images/haaland03.jpg"
	import Haaland04 from "../lib/images/haaland04.jpg"
	import Haaland05 from "../lib/images/haaland05.jpg"
</script>

<svelte:head>
	<title>Home : Haaland or Blonde Hair Woman</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
	
	<h1>Haaland or Blonde Hair Woman</h1>

	<div class="imgBox">
		<img src={Haaland01} alt="">
	</div>
</section>

<style>
	h1 {
		text-align: center;
	}

	.imgBox {
		overflow: hidden;
		margin: 0 auto;
		width: 320px;
	}

	img {
		max-height: 400px;
		max-width: 400px;
		transform-origin: top right;
		transform: scale(3);
	}
</style>


