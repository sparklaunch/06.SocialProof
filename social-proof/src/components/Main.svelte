<script lang="ts">
    import Header from "./Header.svelte";
    import Footer from "./Footer.svelte";
    export let ratings;
</script>

<div id="main">
    <Header {ratings} />
    <Footer />
</div>

<style>
    #main {
        display: flex;
        flex-direction: column;
        width: 80%;
    }
</style>
