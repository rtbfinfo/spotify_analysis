<script lang="ts">
    export let step: Number;
    export let title: String;
    export let currentStep: Number;
    export let Duration: String;
    export let bigSeconds: boolean;
    export let date: String;
    export let introLength: String;
    export let songSource: String;
    export let end: Number;

    import { slide, fade } from 'svelte/transition';
    import { sound } from '../store';

    let autoplay = 0;
    let mute = 1;

    
    let sound_value: boolean

    $: sound.subscribe((value) => {
        sound_value = value;
    });

    $: if (sound_value){
        autoplay = 1
        mute = 0;
    } else {
        autoplay = 0
        mute = 1;
    }
    
</script>

<div class="bg-cardBg rounded-lg gap-2 p-4 w-full md:w-96 flex flex-col justify-center items-center  hover:opacity-100 {currentStep == step ? "opacity-100" : bigSeconds ? "opacity-100" : "opacity-50"} transition-all duration-500"
    transition:slide
   >
    <h1 class="font-semibold text-text text-xl">{@html title}</h1>
    {#if bigSeconds}
    <div transition:slide class="flex gap-4 justify-items-end items-center">
        <h3 class="font-semibold text-4xl text-text">{date}</h3>
        <h2 class="text-8xl font-semibold {step == 0 ? "text-primary" : step == 1 ? "text-graphicPink" : "text-secondary"}">{@html introLength}</h2>
    </div>
    {:else}
    <div transition:slide class="flex gap-4 justify-items-end items-center">
            {#if step == currentStep}
            <iframe transition:fade src="https://www.youtube.com/embed/{songSource}?ecver=1&amp;autoplay={autoplay}&amp;iv_load_policy=3&amp;rel=0&amp;showinfo=0&amp;autohide=1&amp;color=red&amp;start=0&amp;end={end}&amp;width=560&amp;width=560&amp;controls=0&amp;modestbranding=1&amp;mute={mute}&amp;" width="250" height="142" title="embed youtube vidéo du clip de la chanson" allowtransparency={true} frameborder="0"></iframe>
            <p class="text-text text-sm font-semibold">{Duration}</p>
            {/if}
        </div>
    {/if}
</div>

<style>
        iframe {
        border-radius: 10px;

}
</style>