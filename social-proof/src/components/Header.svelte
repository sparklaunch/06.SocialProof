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
    }
</style>
