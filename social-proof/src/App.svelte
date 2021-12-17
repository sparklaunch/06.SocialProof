<script lang="ts">
    import Main from "./components/Main.svelte";
    $: innerWidth = 0;
    $: isMobile = innerWidth <= 1440;
    interface Rating {
        stars: number;
        reviewer: string;
    }
    const ratings: Rating[] = [
        {
            stars: 5,
            reviewer: "Reviews",
        },
        {
            stars: 5,
            reviewer: "Report Guru",
        },
        {
            stars: 5,
            reviewer: "BestTech",
        },
    ];
</script>

<svelte:window bind:innerWidth />
<svelte:head>
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" />
    <link
        href="https://fonts.googleapis.com/css2?family=Spartan:wght@400;500;700&display=swap"
        rel="stylesheet"
    />
</svelte:head>
<div id="app">
    <div id="background-top">
        <img
            src="/assets/bg-pattern-top-{isMobile ? 'mobile' : 'desktop'}.svg"
            alt="Background Top Pattern"
        />
    </div>
    <div id="background-bottom">
        <img
            src="/assets/bg-pattern-bottom-{isMobile
                ? 'mobile'
                : 'desktop'}.svg"
            alt="Background Bottom Pattern"
        />
    </div>
    <div id="wrapper">
        <Main {ratings} />
    </div>
</div>

<style>
    #app {
        width: 100vw;
        height: 100vh;
        position: relative;
    }
    #background-top > img {
        position: absolute;
        width: 100%;
        top: -25vh;
        left: 0;
    }
    #background-bottom > img {
        position: absolute;
        width: 100%;
        bottom: -25vh;
        right: 0;
    }
    #wrapper {
        position: relative;
        z-index: 1;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    @media all and (max-width: 1440px) {
        #background-top > img {
            top: 0;
        }
        #background-bottom > img {
            bottom: 0;
        }
    }
</style>
