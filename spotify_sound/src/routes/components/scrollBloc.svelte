<script lang="ts">
    import CardWave from "./CardWave.svelte";
    import Scroll from "./Scrolly.svelte";
    import { fly } from 'svelte/transition';
    import { afterUpdate } from "svelte";

    const steps = [0, 1, 2];
    let currentStep: Number;
</script>

<section>
    <div class="sticky top-0">
        <div class="mx-3 flex gap-10 flex-col justify-center items-center h-screen">
            <CardWave step=0
            currentStep={currentStep}
            title="Base"/>
            {#if currentStep ==1 || currentStep ==2}
                <CardWave 
                step=1
                currentStep={currentStep}
                title="Intro" 
                />
            {/if}
            {#if currentStep ==2 }
                <CardWave 
                currentStep={currentStep}
                step=2
                title="Couplet"/>

            {/if}
        </div>
    </div>
  
    <Scroll bind:value={currentStep}>
      {#each steps as text, i}
        <div class="flex place-items-center justify-center h-screen" class:active={currentStep === i}>
          <div class="text-text flex justify-center z-10 flex-col bg-background p-2 rounded-lg bg-opacity-50">
            {@html text}
          </div>
        </div>
      {/each}
    </Scroll>
  </section>



