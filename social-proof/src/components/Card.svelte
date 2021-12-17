<script lang="ts">
    export let testimonial;
    export let index;
    type VerticalPosition = "normal" | "below" | "much-below";
    let verticalPosition: VerticalPosition;
    switch (index) {
        case 0:
            verticalPosition = "normal";
            break;
        case 1:
            verticalPosition = "below";
            break;
        case 2:
            verticalPosition = "much-below";
            break;
        default:
            break;
    }
</script>

<div class="card {verticalPosition}">
    <div class="card-title">
        <div class="card-profile">
            <img src="/assets/{testimonial.profile}" alt={testimonial.name} />
        </div>
        <div class="card-name">
            <p>{testimonial.name}</p>
            <p>{testimonial.occupation}</p>
        </div>
    </div>
    <div class="card-content">
        <p>{testimonial.content}</p>
    </div>
</div>

<style>
    .card {
        background-color: rgb(72, 29, 71);
        border-radius: 10px;
        padding: 35px;
    }
    .card-title {
        display: flex;
        align-items: center;
        margin-bottom: 30px;
    }
    .card-name > p:first-child {
        color: white;
        font-weight: 700;
        font-size: 14px;
        margin-bottom: 5px;
    }
    .card-name > p:last-child {
        color: white;
        opacity: 0.3;
        font-weight: 300;
        font-size: 14px;
    }
    .card-profile {
        margin-right: 20px;
    }
    .card-profile > img {
        border-radius: 50%;
        width: 50px;
        height: auto;
    }
    .card-content > p {
        color: white;
        font-size: 14px;
        line-height: 1.6;
    }
    .card-content > p::before {
        content: '" ';
    }
    .card-content > p::after {
        content: ' "';
    }
    .normal {
        transform: translateY(-80px);
    }
    .below {
        transform: translateY(-40px);
    }
    .much-below {
        transform: translateY(0);
    }
</style>
