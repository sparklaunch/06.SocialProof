<script lang="ts">
    import Header from "./Header.svelte";
    import Footer from "./Footer.svelte";
    export let ratings;
    export let testimonials;
</script>

<div id="main">
    <Header {ratings} />
    <Footer {testimonials} />
</div>

<style>
    #main {
        display: flex;
        flex-direction: column;
        width: 80%;
        margin: auto;
    }
    @media all and (max-width: 1440px) {
        #main {
            width: 90%;
        }
    }
</style>
