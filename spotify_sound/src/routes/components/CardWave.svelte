<script lang="ts">
    export let step: Number;
    export let title: String;
    export let currentStep: Number;
    import { fly } from 'svelte/transition';

</script>

<div class="bg-cardBg rounded-lg gap-2 p-4 flex flex-col justify-center items-center {currentStep == step ? "opacity-100" : "opacity-50 transition-all"}"
    transition:fly|local={{ delay: 250, duration: 300, y: 500}}>
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