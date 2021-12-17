<script lang="ts">
    import Rating from "./Rating.svelte";
    export let ratings;
</script>

<div id="header-right">
    <div id="ratings">
        {#each ratings as rating}
            <Rating data={rating} />
        {/each}
    </div>
</div>

<style>
    #header-right {
        width: 50%;
    }
    #ratings {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
    }
</style>
