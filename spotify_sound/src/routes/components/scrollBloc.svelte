<script lang="ts">
    import { fly } from 'svelte/transition';
    import { afterUpdate } from "svelte";
    import Scroll from "./Scrolly.svelte";
    import Song1 from './song1.svelte';
    import Song2 from './song2.svelte';
    import Song3 from './song3.svelte';
    import Youtube from './youtube.svelte';

    const steps = ["Ecoutez cet extrait de «&nbsp;Nothing’s Gonna Stop Us Now&nbsp;», un titre du groupe américain Starship sorti en 1987. Une fois que l'intro s'arrête, scrollez vers le bas pour passer à la musique suivante."
                  , "Et maintenant, faisons un bond dans le temps et passons à cette chanson de Miley Cyrus sortie en 2023. Il n’y a pas quelque chose qui vous frappe ? Scrollez encore vers l'étape suivante..."
                  , "Allez, faisons encore plus évident avec «&nbsp;Where Are You Now&nbsp;», le tube du DJ belge Lost Frequencies souligné par la voix du Britannique Calum Scott. Fin août dernier, ce titre dépassait le milliard d’écoutes sur Spotify… Non ? Toujours pas ?"
                  , "Vous l’avez compris maintenant: l’introduction est à chaque fois plus courte. Ces trois titres choisis pas tout à fait au hasard représentent en fait bien une évolution dans la façon de composer des tubes." ]
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
        <div class="mx-3 flex gap-10 flex-col justify-center items-center h-screen shrink-0 lg:flex-row">
          {#if currentStep >= 0 }
            <Youtube step=0
              currentStep={currentStep}
              title="Starship <span class='text-sm font-light'>Nothing's Gonna Stop Us Now</span>"
              Duration="4:30"
              bigSeconds={bigSeconds}
              date="1987"
              introLength="22<span class='text-5xl font-semibold'>s</span>"
              songSource="3wxyN3z9PL4"
              end=22
              />
              {#if currentStep == 1 || currentStep == 2 || currentStep == 3}
                <Youtube step=1
                currentStep={currentStep}
                title="Miley Cyrus <span class='text-sm font-light'>Flowers</span>"
                Duration="3:20"
                bigSeconds={bigSeconds}
                date="2023"
                introLength="8<span class='text-5xl font-semibold'>s</span>"
                songSource="G7KNmW9a75Y"
                end=10
                />
              {/if}
              {#if currentStep == 2 || currentStep == 3}
                <Youtube step=2
                currentStep={currentStep}
                title="Lost Frequencies <span class='text-sm font-light'>Where Are You Now</span>"
                Duration="2:28"
                bigSeconds={bigSeconds}
                date="2021"
                introLength="0<span class='text-5xl font-semibold'>s</span>"
                songSource="PoP2Sa7wYNQ"
                end=7
                />
              {/if}
            {/if}
        </div>
    </div>
  
    <Scroll bind:value={currentStep}>
      {#each steps as text, i}
        <div class="flex place-items-center justify-center h-screen" class:active={currentStep === i}>
          <div class="text-text flex justify-center z-10 flex-col bg-background rounded-lg bg-opacity-80 w-screen md:w-1/2 p-4">
            {@html text}
          </div>
        </div>
      {/each}
    </Scroll>
  </section>



