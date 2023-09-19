<script lang="ts">
    import { fade } from 'svelte/transition';
    import CardWave from "./CardWave.svelte";
    import Scroll from "./Scrolly.svelte";
    import WaveAnim from './WaveAnim.svelte';

    const steps = ["<p> Allons un peu plus dans le détail. Voici une chanson pop type comme on en fait depuis des années. La recette a longtemps été synonyme de succès&nbsp;: on installe tranquillement le thème avec une longue intro, puis un couplet… et enfin arrive le refrain. Dans le milieu on appelle ça la formule <span class='font-extrabold'><span class='text-graphicPurple'>A</span><span class='text-primary'>B</span><span class='text-graphicPurple'>A</span><span class='text-primary'>B</span><span class='text-secondary'>C</span><span class='text-primary'>B</span></span></p> "
                  , "Mettons de côté la structure quelques instants pour nous concentrer sur la durée."
                  , '<p> Dans de nombreux morceaux récents, l’intro a rétréci. Désormais on entre plus vite dans le vif du sujet avec quelque chose de punchy.</p>'
                  , "<p>Le morceau est lui aussi globalement plus court.<p>"
                  , "<p>Une nouvelle forme fait son apparition, c’est la <span class='font-extrabold'><span class='text-primary'>B</span><span class='text-graphicPurple'>A</span><span class='text-primary'>B</span><span class='text-graphicPurple'>A</span><span class='text-primary'>B</span><span class='text-secondary'>C</span><span class='text-primary'>B</span></span> avec un refrain qui arrive plus tôt pour maintenir l’attention pendant au moins 30 secondes…</p>"
                  ,"<p class='text-bold text-xl text-center max-w-2xl'> Des intros plus courtes, des morceaux moins longs… Vous ne nous croyez pas ? Nous allons vous le prouver par les chiffres. </p>"
                ]
    $: currentStep = 0;

</script>

<section>
    <div class="sticky top-0">
        <div class="mx-3 flex gap-10 flex-col justify-center items-center h-screen shrink-0">
          {#if currentStep == undefined}
          <div transition:fade class="flex flex-col items-center gap-4 absolute top-0 text-text">
            <p>scrollez</p>
            <svg width="47" class="motion-safe:animate-bounce " height="46" viewBox="0 0 47 46" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path fill-rule="evenodd" clip-rule="evenodd" d="M46.8889 23C46.8889 10.2975 36.5914 -4.50116e-07 23.8889 -1.00536e-06C11.1863 -1.56061e-06 0.888885 10.2974 0.888884 23C0.888884 35.7025 11.1863 46 23.8889 46C36.5914 46 46.8889 35.7025 46.8889 23ZM16.6551 18C15.8778 18 15.3977 18.848 15.7976 19.5145L23.0314 31.5708C23.4198 32.2182 24.358 32.2182 24.7464 31.5708L31.9802 19.5145C32.3801 18.848 31.9 18 31.1227 18L23.8889 18L16.6551 18Z" fill="white"/>
              </svg>
          </div>
          {/if}

            <CardWave
              step=0
              currentStep={currentStep}
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
        <div class="flex place-items-start justify-center h-screen" class:active={currentStep === i}>
          <div class="text-text flex justify-center z-10 bg-background rounded-lg bg-opacity-80 w-screen p-4 md:w-1/3">
            {@html text}
          </div>
        </div>
      {/each}
    </Scroll>
  </section>



