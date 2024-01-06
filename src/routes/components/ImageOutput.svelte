<!-- +++++ js +++++ -->
<script>
    import Haaland01 from "../../lib/images/haaland01.webp"
	// import Haaland02 from "../lib/images/haaland02.webp"
	// import Haaland03 from "../lib/images/haaland03.jpg"
	// import Haaland04 from "../lib/images/haaland04.jpg"
	// import Haaland05 from "../lib/images/haaland05.jpg"
    // import GetRamdomNumber from "./RandomNumber.svelte";

    let url = `https://pixabay.com/api/?key=${import.meta.env.VITE_PIXABAY_API_KEY}&q=金髪`
    let getData = fetch(url).then(res => res.json())

    // let getRamdomNumber = new GetRamdomNumber(5,1);

    
    
</script>
<!-- +++++ end +++++ -->
<!-- +++++ html +++++ -->
<!-- {#if }
    
{/if} -->


<div class="imgBox">
    <!-- <img src={Haaland01} alt=""> -->
    {#await getData}
        <p>取得中</p>
    {:then resolveData}
        <img src={resolveData.hits[0].largeImageURL} alt={resolveData.hits[0].tags} width="320" height="320">
    {/await}
</div>
<!-- +++++ end +++++ -->
<!-- +++++ css +++++ -->
<style>
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
<!-- +++++ end +++++ -->