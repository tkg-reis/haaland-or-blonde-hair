<!--+++++++++++++ js ++++++++++++++++++++-->
<script>
	const headerItems = [ 
		"home" , "about" , "opinion"
	]
</script>
<!-- +++++++++++++++++++++++++++++++++++++ -->

<!-- +++++++++++++ html +++++++++++++++++++++ -->
<header>
	<ul>
		{#each headerItems as headerItem , i}
			<li>
				<a href="/{headerItem == "home" ? "" : "404"}">
					{headerItem}
				</a>
			</li>
		{/each}
	</ul>
</header>

<!-- +++++++++++++++++++++++++++++++++++++++ -->

<!-- +++++++++++++++++++++ css ++++++++++++++++++ -->
<style>
	header {
		margin: 0 auto;
		width: 800px;
		max-width: 800px;
	}
	ul {
		display: flex;
		justify-content: center;
		align-items: center;
		gap: 30px;
		list-style: none;
	}
</style>

<!-- +++++++++++++++++++++++++++++++++++++; -->