<script lang="ts">
    import { fade } from 'svelte/transition';
    import Scroll from "./Scrolly.svelte";
    import Youtube from './youtube.svelte';

    const steps = ["Ecoutez cet extrait de «&nbsp;Nothing’s Gonna Stop Us Now&nbsp;», un titre du groupe américain Starship sorti en 1987. Une fois que l'intro s'arrête, scrollez vers le bas pour passer à la musique suivante."
                  , "Et maintenant, faisons un bond dans le temps et passons à cette chanson de Miley Cyrus sortie en 2023. Il n’y a pas quelque chose qui vous frappe ? Scrollez encore vers l'étape suivante..."
                  , "Allez, faisons encore plus évident avec «&nbsp;Where Are You Now&nbsp;», le tube du DJ belge Lost Frequencies souligné par la voix du Britannique Calum Scott. Fin août dernier, ce titre dépassait le milliard d’écoutes sur Spotify… Non ? Toujours pas ?"
                  , "Vous l’avez compris maintenant: l’introduction est à chaque fois plus courte. Ces trois titres choisis pas tout à fait au hasard représentent en fait bien une évolution dans la façon de composer des tubes." ]
                  let currentStep = 0;
    let bigSeconds = false;
    $: console.log(currentStep);

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
            <Youtube step={0}
              currentStep={currentStep}
              title="Starship <span class='text-sm font-light'>Nothing's Gonna Stop Us Now</span>"
              Duration="4:30"
              bigSeconds={bigSeconds}
              date="1987"
              introLength="22<span class='text-5xl font-semibold'>s</span>"
              songSource="3wxyN3z9PL4"
              end={22}
              />
              {#if currentStep == 1 || currentStep == 2 || currentStep == 3}
                <Youtube step={1}
                currentStep={currentStep}
                title="Miley Cyrus <span class='text-sm font-light'>Flowers</span>"
                Duration="3:20"
                bigSeconds={bigSeconds}
                date="2023"
                introLength="8<span class='text-5xl font-semibold'>s</span>"
                songSource="G7KNmW9a75Y"
                end={8}
                />
              {/if}
              {#if currentStep == 2 || currentStep == 3}
                <Youtube step={2}
                currentStep={currentStep}
                title="Lost Frequencies <span class='text-sm font-light'>Where Are You Now</span>"
                Duration="2:28"
                bigSeconds={bigSeconds}
                date="2021"
                introLength="0<span class='text-5xl font-semibold'>s</span>"
                songSource="PoP2Sa7wYNQ"
                end={7}
                />
              {/if}
            {/if}
            {#if currentStep == undefined || currentStep == 0}
            <div transition:fade class="flex flex-col items-center gap-4 absolute top-10 text-text">
              <p>scrollez</p>
              <svg width="47" class="motion-safe:animate-bounce " height="46" viewBox="0 0 47 46" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path fill-rule="evenodd" clip-rule="evenodd" d="M46.8889 23C46.8889 10.2975 36.5914 -4.50116e-07 23.8889 -1.00536e-06C11.1863 -1.56061e-06 0.888885 10.2974 0.888884 23C0.888884 35.7025 11.1863 46 23.8889 46C36.5914 46 46.8889 35.7025 46.8889 23ZM16.6551 18C15.8778 18 15.3977 18.848 15.7976 19.5145L23.0314 31.5708C23.4198 32.2182 24.358 32.2182 24.7464 31.5708L31.9802 19.5145C32.3801 18.848 31.9 18 31.1227 18L23.8889 18L16.6551 18Z" fill="white"/>
                </svg> 
            </div>
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



