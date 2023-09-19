<script>
    export let content;
    export let color;
</script>

<div class="wrapper font-extrabold {color} border-l-[10px] rounded-xl" >
    <p>"{content}"</p>
</div>

<style>

        .wrapper {
        max-width: 50rem;
        margin-inline: auto;
        margin-block: 1rem;
        font-size: 20px;
        color: white;
        padding-inline: 1rem;
    }
</style>