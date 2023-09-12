<script lang="ts">
    import { fade } from 'svelte/transition';
    import { inview } from 'svelte-inview';
    import type { ObserverEventDetails, ScrollDirection, Options } from 'svelte-inview';
    
    export let size: String;
    export let title: String;
    export let textContent: String;
    export let flourishId: String;

    let classes ="";
    let isInView: boolean;

    if(size == "small") {
        classes = "md:flex md:flex-row md:items-center md:gap-4"
    }
    if(size =="small-inverse") {
        classes = "md:flex md:flex-row-reverse md:items-center md:gap-4"
    }



</script>


<!-- <div class="wrapper mt-8"
    use:inview={{ unobserveOnEnter: true, rootMargin: '-20%' }}
    on:inview_change={(event) => {
        let { inView, entry, scrollDirection, observer, node} = event.detail;
        isInView = inView;
        scrollDirection = scrollDirection.vertical;
      }}>
  {#if isInView} -->
    <div  in:fade class="bg-cardBg rounded-lg mx-3 p-2 text-text my-10 {classes} py-2">
        <div class="bg-background rounded-lg md:basis-1/2 mx-auto">
            <iframe src='https://flo.uri.sh/visualisation/{flourishId}/embed' title='Interactive or visual content' frameborder='0' scrolling='no' style='width:100%;' class="h-80 md:h-96 p-1"sandbox='allow-same-origin allow-forms allow-scripts allow-downloads allow-popups allow-popups-to-escape-sandbox allow-top-navigation-by-user-activation'></iframe>
        </div>
        <div class="md:basis-1/2 py-4">
            <h1 class="text-2xl">{title}</h1>
            <p class="text-lg font-light">{textContent}</p>
        </div>
    </div>
  <!-- {/if}
</div> -->
