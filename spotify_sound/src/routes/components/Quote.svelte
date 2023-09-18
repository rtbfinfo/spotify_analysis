<script>
    export let content = String;
    export let color = String;
</script>
<div class="wrapper font-extrabold border-primary only:{color}" >
    <p>"{content}"</p>
</div>

<style>
    p {
        text-align: left;
        border-left: 10px solid;
        padding-left: 0.5rem;
        border-radius: 0.5rem;

    }
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