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
				<a href="/{headerItem == "home" ? "" : headerItem}">
					{headerItem}
				</a>
			</li>
		{/each}
	</ul>
</header>

<!-- +++++++++++++++++++++++++++++++++++++++ -->

<!-- +++++++++++++++++++++ css ++++++++++++++++++ -->
<style>
	
	ul {
		display: flex;
		justify-content: center;
		align-items: center;
		gap: 30px;
		list-style: none;
	}
</style>

<!-- +++++++++++++++++++++++++++++++++++++; -->