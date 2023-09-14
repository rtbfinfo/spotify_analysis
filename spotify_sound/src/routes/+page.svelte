<script lang="ts">
    import Lenis from '@studio-freight/lenis';
    import { onMount } from 'svelte';

    import ScrollBloc from "./components/scrollBloc.svelte";
    import Hero from "./components/Hero.svelte";
    import Title from "./components/Title.svelte";
    import CardGraph from "./components/cardGraph.svelte";
    import ScrollExemple from './components/ScrollStructure.svelte';
    import SoundButton from './components/soundButton.svelte';

    onMount(()=> {
    //smooth scroll 
    const lenis = new Lenis()

    lenis.on('scroll', (e) => {
    })

    function raf(time) {
    lenis.raf(time)
    requestAnimationFrame(raf)
    }

    requestAnimationFrame(raf)

    })

</script>

<Hero/>            
<div class="h-screen bg-background rounded-2xl relative shadow-[ 0px_-20px_14px_-8px_rgba(5,247,130,0.78)]">
    <div class="max-w-3xl text-text px-4 pt-12 mx-auto text-lg">
        <p class="pt-6 first-letter:text-7xl first-letter:mr-3 first-letter:float-left">Il est petit, rond, vert barré de traits noirs et il a changé la musique pour toujours. Le 7 octobre 2008, Spotify était lancé en version publique. Le but de cette plate—frome imaginé par les Suédois Daniel Ek et Martin Lorentzon : de la musique à volonté moyennant des publicités ou un abonnement mensuel.</p>
        <p class="pt-6">La force de Spotify, c’est son algorithme qui vous connait mieux que ne vous connaissait votre médiathécaire dans les années 90. Au point de vous proposer exactement ce que vous avez envie d’entendre au moment où votre humeur le demande. Avec un revers à la médaille : vous enfermer dans des genres musicaux qui vous plaisent.</p>
        <p class="pt-6">Du côté des artistes aussi, les choses ont changé. Du côté de la rémunération d’abord - quelques poignées de centimes par écoute sur Spotify - mais aussi dans la manière de composer de la musique. Vous allez le voir dans ce grand format qui compile des milliers de données : tout est une question de secondes…</p>
            <SoundButton />
    </div>
    <ScrollBloc />
    <ScrollExemple />
    <section class="Pourquoi max-w-4xl mx-auto mb-20">
        <Title
            txt="Pourquoi c'est comme ça ?"
            partie={1}
            color="bg-primary"/>
        <div class="max-w-4xl text-text px-4 mx-auto text-lg">
            <p class="pb-2 pt-6">Lorem ipsum dolor sit amet consectetur.
                Libero nulla morbi cursus nibh mi aliquet augue elit risus. 
                Cras bibendum volutpat nisi sem hendrerit commodo et. 
                Massa donec libero sed eget eget. Consectetur natoque sit vitae magna 
                vitae netus aliquet eget. Commodo diam tincidunt placerat dictumst lobortis. 
                Quisque varius odio dis at dignissim nam. Leo neque fermentum.</p>
        </div>
        <CardGraph 
            size="small"
            title="les genres les plus populaires"
            flourishId="14990472"
            textContent="Lorem ipsum dolor sit amet consectetur.
            Libero nulla morbi cursus nibh mi aliquet augue elit risus. 
            Cras bibendum volutpat nisi sem hendrerit commodo et. 
            Massa donec libero sed eget eget. Consectetur natoque sit vitae magna 
            vitae netus aliquet eget. Commodo diam tincidunt placerat dictumst lobortis. 
            Quisque varius odio dis at dignissim nam. Leo neque fermentum."/>
        <CardGraph 
            size="big"
            flourishId="14936027"
            title="L'évolution de la durée"
            textContent="Lorem ipsum dolor sit amet consectetur.
            Libero nulla morbi cursus nibh mi aliquet augue elit risus. 
            Cras bibendum volutpat nisi sem hendrerit commodo et. 
            Massa donec libero sed eget eget. Consectetur natoque sit vitae magna 
            vitae netus aliquet eget. Commodo diam tincidunt placerat dictumst lobortis. 
            Quisque varius odio dis at dignissim nam. Leo neque fermentum."/>
        <CardGraph 
            size="small"
            flourishId="14990540" 
            title="Durée vs popularité"
            textContent="Lorem ipsum dolor sit amet consectetur.
            Libero nulla morbi cursus nibh mi aliquet augue elit risus. 
            Cras bibendum volutpat nisi sem hendrerit commodo et. 
            Massa donec libero sed eget eget. Consectetur natoque sit vitae magna 
            vitae netus aliquet eget. Commodo diam tincidunt placerat dictumst lobortis. 
            Quisque varius odio dis at dignissim nam. Leo neque fermentum."/>
    </section>
    <section class="max-w-4xl mx-auto mb-20">
        <Title
            txt="le streaming change la musique"
            partie={2}
            color="bg-secondary"/>
        <div class="max-w-4xl text-text px-4 mx-auto text-lg">
            <p class="pb-2 pt-6">Lorem ipsum dolor sit amet consectetur.
                Libero nulla morbi cursus nibh mi aliquet augue elit risus. 
                Cras bibendum volutpat nisi sem hendrerit commodo et. 
                Massa donec libero sed eget eget. Consectetur natoque sit vitae magna 
                vitae netus aliquet eget. Commodo diam tincidunt placerat dictumst lobortis. 
                Quisque varius odio dis at dignissim nam. Leo neque fermentum.</p>
        </div>
        <CardGraph 
            size="small"
            title="Evolution de la durée des intros du billboard hot 100"
            flourishId="14990758"
            textContent="Lorem ipsum dolor sit amet consectetur.
            Libero nulla morbi cursus nibh mi aliquet augue elit risus. 
            Cras bibendum volutpat nisi sem hendrerit commodo et. 
            Massa donec libero sed eget eget. Consectetur natoque sit vitae magna 
            vitae netus aliquet eget. Commodo diam tincidunt placerat dictumst lobortis. 
            Quisque varius odio dis at dignissim nam. Leo neque fermentum."/>
        <CardGraph 
            size="big"
            flourishId="datawrapper"
            title="Evolution de la durée des intros du billboard hot 100"
            textContent="Lorem ipsum dolor sit amet consectetur.
            Libero nulla morbi cursus nibh mi aliquet augue elit risus. 
            Cras bibendum volutpat nisi sem hendrerit commodo et. 
            Massa donec libero sed eget eget. Consectetur natoque sit vitae magna 
            vitae netus aliquet eget. Commodo diam tincidunt placerat dictumst lobortis. 
            Quisque varius odio dis at dignissim nam. Leo neque fermentum."/>
    </section>
       
    <section class="max-w-4xl mx-auto mb-20">
        <Title
            txt="Les réactions de l'industrie"
            partie={3}
            color="bg-graphicPurple"/>
        <div class="max-w-4xl text-text px-4 mx-auto text-lg">
            <p class="pb-12 pt-6">Lorem ipsum dolor sit amet consectetur.
                Libero nulla morbi cursus nibh mi aliquet augue elit risus. 
                Cras bibendum volutpat nisi sem hendrerit commodo et. 
                Massa donec libero sed eget eget. Consectetur natoque sit vitae magna 
                vitae netus aliquet eget. Commodo diam tincidunt placerat dictumst lobortis. 
                Quisque varius odio dis at dignissim nam. Leo neque fermentum.</p>
        </div>
    </section>
   
</div>

