<script lang="ts">

export let txt: String;
export let partie: Number;
export let color: String;

</script>


<div class="flex gap-2 mx-3 pt-4 items-center mt-5">
    <div class="rounded-full {color} w-14 h-20"></div>
    <div class="text-text">
        <h1 class="text-sm opacity-80">PARTIE {partie}</h1>
        <h1 class="text-3xl">{txt}</h1>
    </div>
</div>