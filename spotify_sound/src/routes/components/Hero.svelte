<script lang="ts">

</script>

<div class="text-text text-center h-screen flex flex-col justify-center items-center gap-6 bg-cardBg z-0 sticky top-0">
    <h4 class="text-sm">Décrypte</h4>
    <h1 class="text-6xl font-extrabold tracking-tighter" style="text-wrap: balance;">Comment <span class="text-primary">Spotify</span> a changé la <span class="text-secondary">musique</span></h1>
    <div class="sound-wave flex gap-1 justify-center">
        {#each Array(30) as _, index (index)}
            <div class="w-2 h-20 bg-primary rounded-md"></div>
        {/each}
    </div>
    <h2 class="text-2xl tracking-tight">Sous-titre</h2>
    <h3 class="text-lg bg-cardBg p-2 rounded-lg tracking-tight text-primary max-w-fit bg-opacity-50 hover:bg-opacity-100 transition-all">Ambroise Carton et Héloïse Feldmann</h3>
    <div class="mouse_wheel flex items-center flex-col z-10 absolute bottom-3">
        <div class="anim-scroll border-2 border-text h-10 relative w-5 z-10 rounded-lg"></div>
        <div class="anim-scroll--wheel"></div>
    </div>
</div>
