<!-- +++++ js +++++ -->
<script>
// @ts-nocheck

	import { onMount } from "svelte";

// @ts-nocheck

    import Haaland01 from "../../lib/images/haaland01.webp"
	import Haaland02 from "../../lib/images/haaland02.webp"
	import Haaland03 from "../../lib/images/haaland03.jpg"
	import Haaland04 from "../../lib/images/haaland04.jpg"
	import Haaland05 from "../../lib/images/haaland05.jpg"

    let url = `https://pixabay.com/api/?key=${import.meta.env.VITE_PIXABAY_API_KEY}&q=金髪`
    let getData = () =>  fetch(url).then(res => res.json());

	getData();
	$: console.log("hello");

	// @ts-ignore
	// image domの初期値
	let imageDom ;
	const vals = ["Haaland" , "BlondeHairWoman"];
	const imgs = [Haaland01, Haaland02, Haaland03, Haaland04, Haaland05];
	
	function viewAnswer() {
		// @ts-ignore
		// console.log(imageDom);
		// ボタン処理と同時に同期処理で画像のスクリーンアウト処理
		imageDom.style.transform = "scale(1)";

		// 5秒後に画像をスクリーンイン処理
		const screenIn = setTimeout(() => {
			imageDom.style.transform = "scale(3)";
			getData();
		}, 5000);
		
		// バグ回避のため、scrennIn関数を排除処理
		return () => clearTimeout(screenIn);

	}
	$: getData();
	$: console.log("hello");
	$: currentNumber = createRandomNumber(1,20);
	$: getHaalnadPictureNumber = createRandomNumber(1,5);
	$: currentImage = imgs.filter(img => img.includes(getHaalnadPictureNumber));

	/**
	 * @param {number} min
	 * @param {number} max
	 */
	function createRandomNumber(min, max) {
        return Math.floor(Math.random() * (max - min + 1)) + min;
    }

	let currentNumber = createRandomNumber(1,20);
	let getHaalnadPictureNumber = createRandomNumber(1,5);
	let currentImage = imgs.filter(img => img.includes(getHaalnadPictureNumber));
    
</script>
<!-- +++++ end +++++ -->
<!-- +++++ html +++++ -->
<!-- ロジックをもう少し考える -->
<!-- マジックナンバーを回避 -->

{#if currentNumber < 9}
	<div class="imgBox" >
		{#await getData}
			<p>取得中</p>
		{:then resolveData}
			<img src={resolveData.hits[1].largeImageURL} alt={resolveData.hits[1].tags} width="320" height="320" bind:this={imageDom}>
		{/await}
	</div>
{:else if currentNumber > 10}
	<div class="imgBox" >
		<img src={currentImage} alt="haaland" bind:this={imageDom}>
	</div>
{/if}

<div>
	{#each vals as val}
    <button on:click={viewAnswer}>
        {val}
    </button>
    {/each}
</div>


<!-- +++++ end +++++ -->
<!-- +++++ css +++++ -->
<style>

	div {
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
		/* top leftとかに変更できるようにする */
		transform-origin: top right;
		transform: scale(3);
	}
</style>
<!-- +++++ end +++++ -->