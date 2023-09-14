<script lang="ts">
    export let step: Number;
    export let title: String;
    export let currentStep: Number;
    import { slide } from 'svelte/transition';
    import { flip } from 'svelte/animate';

    let transition = "transition:slide"
    if (currentStep == 0) {
        transition = "in:slide"
    }
</script>

<div class="bg-cardBg rounded-lg gap-0 p-4 flex flex-col w-full md:w-96 justify-center items-center  hover:opacity-90 {currentStep == step ? "opacity-100" : "opacity-50 transition-all duration-500"}"
    transition:slide
   >
    <!-- <h1 class="font-semibold text-text text-xl">{title}</h1> -->
    {#if step == 0}
    <img src="/sound/ABABCB.svg" alt="onde sonore montrant la composition ABABCB"/>
    {/if}
    {#if step == 1}
    <img src="/sound/intro_courte.svg" alt="onde sonore montrant la composition ABABCB"/>
    {/if}
    {#if step == 2}
    <img src="/sound/BABABCB.svg" alt="onde sonore montrant la composition BABABCB"/>
    {/if}
</div>