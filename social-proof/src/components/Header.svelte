<script lang="ts">
    import HeaderLeft from "./HeaderLeft.svelte";
    import HeaderRight from "./HeaderRight.svelte";
    export let ratings;
</script>

<div id="header">
    <HeaderLeft />
    <HeaderRight {ratings} />
</div>

<style>
    #header {
        display: flex;
        align-items: center;
        height: 300px;
        margin-bottom: 100px;
    }
    @media all and (max-width: 1440px) {
        #header {
            flex-direction: column;
            height: auto;
            margin: 0;
        }
    }
</style>
