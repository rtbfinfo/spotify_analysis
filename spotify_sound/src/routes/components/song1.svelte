<script lang="ts">
    export let step: Number;
    export let title: String;
    export let currentStep: Number;
    export let Duration: String;
    export let bigSeconds: boolean;
    export let date: String;
    export let introLength: String;
    export let songSource: String;

    import { slide, fade } from 'svelte/transition';
    import { flip } from 'svelte/animate';
    import { sound } from '../store';

    let paused = true;
    let time = 0;
    let duration;
    $: progress = (time / duration);

    
    let sound_value: boolean

    $: sound.subscribe((value) => {
        sound_value = value;
    });

    $: if (sound_value){

    if(currentStep == step) {
        paused = false;
    } else {
        paused = true;
    }
    }

    const playVideo = () => {
        if (sound_value){
        paused = !paused;
        }
    }
    
    //revenir au début de la chanson quand la progress bar est à la fin
    $: if ( progress == 1 && paused == true) {
    progress = 0;
   }
  
    $: console.log(paused)
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
        <!-- <button class="rounded-full bg-text w-10 h-10 hover:opacity-60" on:click={playVideo}>
            {#if !paused}
            <svg xmlns="http://www.w3.org/2000/svg" class="h-9 w-10 text-background" viewBox="0 0 20 20" fill="currentColor">
                <path fill-rule="evenodd" d="M5 4h3v12H5V4zm7 0h3v12h-3V4z" clip-rule="evenodd" />
            </svg>
            {:else}
            <svg xmlns="http://www.w3.org/2000/svg" class="h-9 w-10 text-background" viewBox="0 0 20 20" fill="currentColor">
                <path fill-rule="evenodd" d="M8 5v10l7-5-7-5z" clip-rule="evenodd" />
            </svg>
            {/if}
        </button> -->
        <audio src="https://rtbfmedia.be/rtbfinfo/songs_intro/{songSource}.mp3" 
        playsinline
        bind:paused={paused} 
        bind:currentTime={time}
		bind:duration />   
            <progress id="progress" value={progress || 0} min="0" class="{step == 0 ? "bg-primary" : step == 1 ? "bg-graphicPink" : "bg-secondary"} "></progress>    
        
    </div>
    {/if}
</div>

<style>
    
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