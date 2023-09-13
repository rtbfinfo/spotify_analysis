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

<div class="bg-cardBg rounded-lg gap-2 p-4 flex flex-col justify-center items-center  hover:opacity-90 {currentStep == step ? "opacity-100" : "opacity-50 transition-all duration-500"}"
    transition:slide
   >
    <h1 class="font-semibold text-text text-xl">{title}</h1>
    <div class="flex gap-1 justify-items-end">
        <img src="./sound/intro.svg" alt="découpage de l'intro" style="opacity: {step == 0 ? 100 : 0}; transition-all">
        <img src="./sound/couplet1.svg" alt="découpage du premier couplet">
        <img src="./sound/refrain.svg" alt="découpage du refrain">
        <img src="./sound/couplet2.svg" alt="découpage du deuxieme couplet">
        <img src="./sound/refrain.svg" alt="découpage du refrain">
        <img src="./sound/pont.svg" alt="découpage du pont">
        <img src="./sound/refrain.svg" alt="découpage du refrain" style="opacity: {step == 2 ? 0 : 100};">
    </div>
</div>