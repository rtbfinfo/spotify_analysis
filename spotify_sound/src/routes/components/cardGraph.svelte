<script lang="ts">
    import { fade } from 'svelte/transition';
    
    export let size: String;
    export let title: String;
    export let textContent: String;
    export let flourishId: String;

    let classes ="";

    if(size == "small") {
        classes = "md:flex md:flex-row md:items-center md:gap-4"
    }
    if(size =="small-inverse") {
        classes = "md:flex md:flex-row-reverse md:items-center md:gap-4"
    }



</script>

    <div  in:fade class="bg-cardBg rounded-lg mx-3 p-2 text-text my-10 {classes} py-2">
        {#if flourishId == "14991590"}
        <div class="iframe-container bg-background rounded-lg md:basis-1/2 mx-auto">
            <iframe src='https://flo.uri.sh/visualisation/14991590/embed' title='Interactive or visual content' class='flourish-embed-iframe' frameborder='0' scrolling='no' style='width:100%;height:600px;' sandbox='allow-same-origin allow-forms allow-scripts allow-downloads allow-popups allow-popups-to-escape-sandbox allow-top-navigation-by-user-activation'></iframe>
       
        <iframe src='https://flo.uri.sh/visualisation/15032377/embed' title='Interactive or visual content' class='flourish-embed-iframe' frameborder='0' scrolling='no' style='width:100%;height:600px;' sandbox='allow-same-origin allow-forms allow-scripts allow-downloads allow-popups allow-popups-to-escape-sandbox allow-top-navigation-by-user-activation'></iframe>
     </div>
        {:else if flourishId == "14936027"}
        <div class="bg-background rounded-lg md:basis-1/2 mx-auto">
            <iframe src='https://flo.uri.sh/visualisation/{flourishId}/embed' title='Interactive or visual content' frameborder='0' scrolling='no' style='width:100%;' class="h-80 md:h-[600px] p-1"sandbox='allow-same-origin allow-forms allow-scripts allow-downloads allow-popups allow-popups-to-escape-sandbox allow-top-navigation-by-user-activation'></iframe>
            </div>
        {:else}
            <div class="bg-background rounded-lg md:basis-1/2 mx-auto">
            <iframe src='https://flo.uri.sh/visualisation/{flourishId}/embed' title='Interactive or visual content' frameborder='0' scrolling='no' style='width:100%;' class="h-80 md:h-96 p-1"sandbox='allow-same-origin allow-forms allow-scripts allow-downloads allow-popups allow-popups-to-escape-sandbox allow-top-navigation-by-user-activation'></iframe>
            </div>
        {/if}

        <div class="md:basis-1/2 py-4">
            <h1 class="text-2xl">{title}</h1>
            <p class="text-lg font-light">{@html textContent}</p>
        </div>
    </div>

<style>
    .iframe-container {
  position: relative;
  width: 100%;
  height: 600px;
}

.iframe-container iframe {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
</style>
