<script lang="ts">
    import Star from "./Star.svelte";
    export let data;
</script>

<div class="rating">
    <div class="stars">
        {#each Array(data.stars) as _}
            <Star />
        {/each}
    </div>
    <div class="reviewer">
        <p>Rated {data.stars} Stars in {data.reviewer}</p>
    </div>
</div>

<style>
    .rating {
        background-color: rgb(245, 240, 245);
        border-radius: 10px;
        padding: 20px 30px;
        display: flex;
        align-items: center;
        margin: 10px 0;
    }
    .stars {
        display: flex;
        margin-right: 50px;
    }
    .reviewer > p {
        color: rgb(72, 29, 71);
        font-weight: 700;
        font-size: 14px;
    }
</style>
