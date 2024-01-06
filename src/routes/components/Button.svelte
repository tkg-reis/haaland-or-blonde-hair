<!-- +++++ js +++++ -->
<script>
    const vals = ["Haaland" , "BlondeHairWoman"];
</script>
<!-- +++++ end +++++ -->
<!-- +++++ html +++++ -->
<div>
    {#each vals as val}
    <button>
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
</style>
<!-- +++++ end +++++ -->
