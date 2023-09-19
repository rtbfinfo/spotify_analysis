<script>
    export let content;
    export let color;
</script>

<div class="wrapper font-extrabold {color} border-l-[10px] pl-2 rounded-xl" >
    <p>"{content}"</p>
</div>

<style>

        .wrapper {
        max-width: 50rem;
        margin-inline: auto;
        margin-block: 1rem;
        font-size: 20px;
        color: white;
        text-align: center;
        padding-inline: 1rem;
    }
</style>