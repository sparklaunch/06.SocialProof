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
