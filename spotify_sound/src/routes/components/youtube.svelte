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
    import { flip } from 'svelte/animate';
    import { sound } from '../store';

    let lost = "PoP2Sa7wYNQ"
    let cyrus = "G7KNmW9a75Y"
    let paused = true;
    let time = 0;
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

    const playVideo = () => {
        if (sound_value){
        paused = !paused;
        }
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
            <iframe transition:fade src="https://www.youtube.com/embed/{songSource}?ecver=1&amp;autoplay={autoplay}&amp;iv_load_policy=3&amp;rel=0&amp;showinfo=0&amp;autohide=1&amp;color=red&amp;start=0&amp;end={end}&amp;width=560&amp;width=560&amp;controls=0&amp;modestbranding=1&amp;mute={mute}&amp;" width="250" height="142" title="embed youtube vidéo du clip de la chanson" allowtransparency="true" modestbranding="1" controls="0" frameborder="0"></iframe>
            <p class="text-text text-sm font-semibold">{Duration}</p>
            {/if}
        </div>
    {/if}
</div>

<style>
        iframe {
        border-radius: 10px;
        /* clip-path: path("M6.8889 11h4.2827s6 0 6 6v64s0 6 -6 6h-4.2827s-6 0 -6 -6v-64s0 -6 6 -6 M35.7456 15h7.5393s6 0 6 6v56s0 6 -6 6h-7.5393s-6 0 -6 -6v-56s0 -6 6 -6 M67.8588 0h7.5393s6 0 6 6v86s0 6 -6 6h-7.5393s-6 0 -6 -6v-86s0 -6 6 -6 M99.9719 11h4.2827s6 0 6 6v64s0 6 -6 6h-4.2827s-6 0 -6 -6v-64s0 -6 6 -6 M128.828 22h4.2827s6 0 6 6v42s0 6 -6 6h-4.2827s-6 0 -6 -6v-42s0 -6 6 -6"); */

}
    	progress {
            clip-path: path("M6.8889 11h4.2827s6 0 6 6v64s0 6 -6 6h-4.2827s-6 0 -6 -6v-64s0 -6 6 -6 M35.7456 15h7.5393s6 0 6 6v56s0 6 -6 6h-7.5393s-6 0 -6 -6v-56s0 -6 6 -6 M67.8588 0h7.5393s6 0 6 6v86s0 6 -6 6h-7.5393s-6 0 -6 -6v-86s0 -6 6 -6 M99.9719 11h4.2827s6 0 6 6v64s0 6 -6 6h-4.2827s-6 0 -6 -6v-64s0 -6 6 -6 M128.828 22h4.2827s6 0 6 6v42s0 6 -6 6h-4.2827s-6 0 -6 -6v-42s0 -6 6 -6");
            height: 100px;
            -webkit-appearance: none;
            appearance: none;
            -moz-appearance: none;
	}

	progress::-webkit-progress-bar {
		background-color: #04C28F;
	}

	progress::-webkit-progress-value {
		background-color: rgba(255, 255, 255, 01);
	}
	progress::-moz-progress-bar {
		background-color: rgba(255, 255, 255, 01);
	}
</style>