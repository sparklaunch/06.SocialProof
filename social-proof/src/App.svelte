<script lang="ts">
    import Main from "./components/Main.svelte";
    $: innerWidth = 0;
    $: isMobile = innerWidth <= 1440;
    interface Rating {
        stars: number;
        reviewer: string;
    }
    interface Testimonial {
        profile: string;
        name: string;
        occupation: string;
        content: string;
    }
    const ratings: Rating[] = [
        {
            stars: 5,
            reviewer: "Reviews"
        },
        {
            stars: 5,
            reviewer: "Report Guru"
        },
        {
            stars: 5,
            reviewer: "BestTech"
        }
    ];
    const testimonials: Testimonial[] = [
        {
            profile: "image-colton.jpg",
            name: "Colton Smith",
            occupation: "Verified Buyer",
            content:
                "We needed the same printed design as the one we had ordered a week prior. Not only did they find the original order, but we also received it in time. Excellent!"
        },
        {
            profile: "image-irene.jpg",
            name: "Irene Roberts",
            occupation: "Verified Buyer",
            content:
                "Customer Service is always excellent and very quick turn around. Completely delighted with the simplicity of the purchase and the speed of delivery."
        },
        {
            profile: "image-anne.jpg",
            name: "Anne Wallace",
            occupation: "Verified Buyer",
            content:
                "Put an order with this company and can only praise them for the very high standard. Will definitely use them again and recommend them to everyone!"
        }
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
<main>
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
        <Main {ratings} {testimonials} />
    </div>
</main>

<style>
    main {
        width: 100vw;
        height: 100vh;
        position: relative;
    }
    #background-top {
        position: absolute;
        top: 0;
        left: 0;
    }
    #background-bottom {
        position: absolute;
        bottom: 0;
        right: 0;
    }
    #background-top > img {
        width: 100%;
    }
    #background-bottom > img {
        width: 100%;
    }
    #wrapper {
        position: relative;
        z-index: 1;
        display: flex;
        justify-content: center;
        align-items: center;
        width: 100vw;
        height: 100vh;
    }
    @media all and (max-width: 1440px) {
        main {
            padding: 100px 0 50px 0;
            margin: auto;
            height: auto;
            width: 100%;
        }
        #wrapper {
            display: block;
            width: 100%;
            height: auto;
        }
    }
</style>
