<script lang="ts">
    import Lenis from '@studio-freight/lenis';
    import { onMount } from 'svelte';

    import ScrollBloc from "./components/scrollBloc.svelte";
    import Hero from "./components/Hero.svelte";
    import Title from "./components/Title.svelte";
    import CardGraph from "./components/cardGraph.svelte";

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
<div class="h-screen bg-background rounded-2xl relative">
    <div class="max-w-4xl text-text px-4 mx-auto text-lg">
        <p class="pt-12">Il est petit, rond, vert barré de traits noirs et il a changé la musique pour toujours. Dans ce grand format data avec plein de jolis graphiques on vous explique pourquoi Spotify a modifié les techniques des artistes pour nous faire consommer de la zik.</p>
    </div>
    <ScrollBloc />
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
            size="small-inverse"
            flourishId="14991036"
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

