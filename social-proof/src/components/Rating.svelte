<script lang="ts">
    import Star from "./Star.svelte";
    export let data;
    export let index;
    let innerWidth: number;
    $: isMobile = innerWidth <= 1440;
    type Position = "backward" | "normal" | "forward";
    let position: Position;
    $: if (isMobile) {
        position = "forward";
    } else {
        switch (index) {
            case 0:
                position = "backward";
                break;
            case 1:
                position = "normal";
                break;
            case 2:
                position = "forward";
                break;
            default:
                break;
        }
    }
</script>

<svelte:window bind:innerWidth />
<div class="rating {position}">
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
        width: 500px;
    }
    .stars {
        display: flex;
        margin-right: 50px;
        width: 100px;
    }
    .reviewer > p {
        color: rgb(72, 29, 71);
        font-weight: 700;
        font-size: 14px;
    }
    .backward {
        transform: translateX(-80px);
    }
    .normal {
        transform: translateX(-40px);
    }
    .forward {
        transform: translateX(0);
    }
    @media all and (max-width: 1440px) {
        .rating {
            flex-direction: column;
            width: 100%;
        }
        .stars {
            justify-content: center;
            width: 100%;
            margin: 0;
            margin-bottom: 10px;
        }
    }
</style>
