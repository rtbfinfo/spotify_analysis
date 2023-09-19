<script lang="ts">
    export let step: Number;
    export let currentStep: Number;
    import { slide } from 'svelte/transition';

</script>

<div class="bg-cardBg rounded-lg gap-0 p-4 flex flex-col w-full md:w-96 justify-center items-center  hover:opacity-90 {currentStep == step ? "opacity-100" : "opacity-50"} transition-all duration-500"
    transition:slide>
    {#if step == 0}
    <img src="./sound/ABABCB.svg" alt="onde sonore montrant la composition ABABCB"/>
    {/if}
    {#if step == 1}
    <img src="./sound/intro_courte.svg" alt="onde sonore montrant la composition ABABCB"/>
    {/if}
    {#if step == 4}
    <img src="./sound/BABABCB.svg" alt="onde sonore montrant la composition BABABCB"/>
    {/if}
</div>