<script lang="ts">
    export let testimonial;
    export let index;
</script>

<div class="card">
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
