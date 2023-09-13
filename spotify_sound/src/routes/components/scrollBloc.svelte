<script lang="ts">
    import { fly } from 'svelte/transition';
    import { afterUpdate } from "svelte";
    import CardWave from "./CardWave.svelte";
    import Scroll from "./Scrolly.svelte";
    import CardSong from "./CardSong.svelte";

    const steps = ["Ecoutez cet extrait de Nothing’s Gonna Stop Us Now un titre du groupe américain Starship sorti en 1987"
                  , "Et maintenant, faisons un bon dans le temps et passons à cette chanson de Miley Cyrus sortie en 2023."
                  , "Il n’y a pas quelque chose qui vous frappe ? Allez, faisons encore plus évident avec Where Are You Now, le tube du DJ belge Lost Frequencies souligné par la voix du Britannique Calum Scott. Fin août, ce titre dépassait le milliard d’écoutes sur Spotify…"
                  , "Vous l’avez compris maintenant: l’intro est à chaque fois plus courte. Ces trois titres choisis pas tout à fait au hasard représentent bien une évolution dans la façon de composer des tubes."];
    let currentStep = 0;
    let bigSeconds = false;

    $: if (currentStep == 3) {
      bigSeconds = true;
    } else {
      bigSeconds = false;
    }
</script>

<section>
    <div class="sticky top-0">
        <div class="mx-3 flex gap-10 flex-col justify-center items-center h-screen shrink-0">
            {#if currentStep == 0 || currentStep == 1 || currentStep == 2 || currentStep == 3}
              <CardSong step=0
              currentStep={currentStep}
              title="Starship <span class='text-sm font-light'>Nothing's Gonna Stop Us Now</span>"
              Duration="3:20"
              bigSeconds={bigSeconds}
              date="1987"
              introLength="22<span class='text-5xl font-semibold'>s</span>"
              songSource="starship"
              />
              {#if currentStep == 1 || currentStep == 2 || currentStep == 3}
                <CardSong step=1
                currentStep={currentStep}
                title="Miley Cyrus <span class='text-sm font-light'>flower</span>"
                Duration="3:20"
                bigSeconds={bigSeconds}
                date="2023"
                introLength="8<span class='text-5xl font-semibold'>s</span>"
                songSource="cyrus"
                />
              {/if}
              {#if currentStep == 2 || currentStep == 3}
                <CardSong step=2
                currentStep={currentStep}
                title="Lost Frequencies <span class='text-sm font-light'>Where Are You Now</span>"
                Duration="3:20"
                bigSeconds={bigSeconds}
                date="2021"
                introLength="0<span class='text-5xl font-semibold'>s</span>"
                songSource="lost_frequencies"
                />
              {/if}
            {/if}
        </div>
    </div>
  
    <Scroll bind:value={currentStep}>
      {#each steps as text, i}
        <div class="flex place-items-center justify-center h-screen" class:active={currentStep === i}>
          <div class="text-text flex justify-center z-10 flex-col bg-background rounded-lg bg-opacity-80 w-screen p-4">
            {@html text}
          </div>
        </div>
      {/each}
    </Scroll>
  </section>



