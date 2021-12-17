<script lang="ts">
    import Rating from "./Rating.svelte";
    export let ratings;
</script>

<div id="header-right">
    <div id="ratings">
        {#each ratings as rating, index}
            <Rating data={rating} {index} />
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
        align-items: flex-end;
    }
    @media all and (max-width: 1440px) {
        #header-right {
            width: 100%;
            margin-bottom: 120px;
        }
        #ratings {
            align-items: center;
        }
    }
</style>
