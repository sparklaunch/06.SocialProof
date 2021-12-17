<script lang="ts">
    import Card from "./Card.svelte";
    export let testimonials;
</script>

<div id="footer">
    <div id="cards">
        {#each testimonials as testimonial, index}
            <Card {testimonial} {index} />
        {/each}
    </div>
</div>

<style>
    #cards {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        column-gap: 30px;
    }
    @media all and (max-width: 1440px) {
        #cards {
            display: flex;
            flex-direction: column;
        }
    }
</style>
