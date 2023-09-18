<script lang="ts">
    import { fly } from 'svelte/transition';
    import { afterUpdate } from "svelte";
    import CardWave from "./CardWave.svelte";
    import Scroll from "./Scrolly.svelte";
    import WaveAnim from './WaveAnim.svelte';

    const steps = ["<p> Allons un peu plus dans le détail. Voici une chanson pop type comme on en a toujours fait pendant des années. La recette a longtemps été synonyme de succès : on installe tranquillement le thème avec une longue intro, puis un couplet… et enfin arrive le refrain. Dans le milieu on appelle ça la formule <span class='font-extrabold'><span class='text-graphicPurple'>A</span><span class='text-primary'>B</span><span class='text-graphicPurple'>A</span><span class='text-primary'>B</span><span class='text-secondary'>C</span><span class='text-primary'>B</span></span></p> "
                  , "Mettons de côté la structure quelques instants…"
                  , '<p> Dans de nombreux morceaux récents, l’intro a rétréci. Désormais on entre plus vite dans le vif du sujet avec quelque chose de punchy.</p>'
                  , "<p>Le morceau est lui aussi globalement plus court.<p>"
                  , "<p>Une nouvelle forme fait son apparition, c’est la <span class='font-extrabold'><span class='text-primary'>B</span><span class='text-graphicPurple'>A</span><span class='text-primary'>B</span><span class='text-graphicPurple'>A</span><span class='text-primary'>B</span><span class='text-secondary'>C</span><span class='text-primary'>B</span></span> avec un refrain qui arrive plus tôt pour maintenir l’attention pendant au moins 30 secondes…</p>"
                  ,"<p class='text-bold text-xl text-center max-w-2xl'> Des intros plus courtes, des morceaux moins longs… Vous ne nous croyez pas ? Nous allons vous le prouver par les datas. </p>"
                ]
    $: currentStep = 0;
    let bigSeconds = false;

    $: console.log(currentStep)

    $: if (currentStep == 3) {
      bigSeconds = true;
    } else {
      bigSeconds = false;
    }
</script>

<section>
    <div class="sticky top-0">
        <div class="mx-3 flex gap-10 flex-col justify-center items-center h-screen shrink-0">
              <CardWave
              step=0
              currentStep={currentStep}
              title="Base"
              />
                {#if currentStep >= 1 && currentStep < 4}
                <WaveAnim
                currentStep={currentStep}
                />
                {/if}
                {#if currentStep >= 4}
                <CardWave 
                step=4
                currentStep={currentStep}
                title="Intro" 
                />
                {/if}
            <div class="grid grid-rows-2 grid-cols-2 gap-2 h-16 w-fit p-2 font-medium bg-cardBg bottom-14 left-auto right-auto absolute {currentStep == 5 ? "opacity-50" : "opacity-100"} flex-wrap rounded-lg">
                <div class="flex gap-1">
                  <div class="h-6 w-6 rounded-lg bg-primary"></div>
                  <h3 class=" text-text">Refrain</h3>
                </div>
                <div class="flex gap-1">
                  <div class="h-6 w-6 rounded-lg bg-graphicPink"></div>
                  <h3 class=" text-text">Intro</h3>
                </div>
                <div class="flex gap-1">
                  <div class="h-6 w-6 rounded-lg bg-graphicPurple"></div>
                  <h3 class=" text-text">Couplet</h3>
                </div>
                <div class="flex gap-1">
                  <div class="h-6 w-6 rounded-lg bg-secondary"></div>
                  <h3 class=" text-text">Pont</h3>
                </div>
            </div>
        </div>
    </div>
  
    <Scroll bind:value={currentStep}>
      {#each steps as text, i}
        <div class="flex place-items-center justify-center h-screen" class:active={currentStep === i}>
          <div class="text-text flex justify-center z-10 bg-background rounded-lg bg-opacity-80 w-screen p-4 md:w-1/3">
            {@html text}
          </div>
        </div>
      {/each}
    </Scroll>
  </section>



