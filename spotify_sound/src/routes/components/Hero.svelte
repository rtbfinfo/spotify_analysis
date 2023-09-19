

<div class="text-text text-center h-screen flex flex-col justify-center items-center gap-8 bg-cardBg z-0 sticky top-0">
    <h4 class="text-sm">Décrypte</h4>
    <h1 class="md:text-6xl text-5xl font-extrabold tracking-tighter max-w-4xl" style="text-wrap: balance;">Comment <span class="text-primary">Spotify</span> a changé la façon de composer la <span class="text-secondary">musique</span></h1>
    <div class="sound-wave flex gap-2 justify-center h-fit w-[99%]">
        {#each Array(25) as _, index (index)}
            <div class=" bar w-2 h-full bg-primary rounded-md overflow-hidden" style="animation-duration:{Math.random() * (1.5 - 0.5) + 0.5}s"></div>
        {/each}
    </div>
    <div class="text-center">
        <h3 class="text-lg bg-cardBg p-2 rounded-lg tracking-tight text-primary max-w-fit bg-opacity-50 hover:bg-opacity-100 transition-all">Par Ambroise Carton, Sarah Heinderyckx et Héloïse Feldmann</h3>
    </div>
    <div class="mouse_wheel flex items-center flex-col z-10 absolute bottom-8">
        <div class="anim-scroll border-2 border-text h-10 relative w-5 z-10 rounded-lg"></div>
        <div class="anim-scroll--wheel"></div>
    </div>
</div>


<style>

.sound-wave {
    height: 100px;
    display: flex;
    align-items: center;
    justify-content: center;
  }

.bar {
    animation-name: wave-lg;
    animation-iteration-count: infinite;
    animation-timing-function: ease-in-out;
    animation-direction: alternate;
  }

  &:nth-child(-n + 7),
    &:nth-last-child(-n + 7) {
      animation-name: wave-md;
    }

    &:nth-child(-n + 3),
    &:nth-last-child(-n + 3) {
      animation-name: wave-sm;
    }
 

    @keyframes wave-sm {
    0% {
        opacity: 0.35;
        height: 30px;
    }
    100% {
        opacity: 1;
        height: 50px;
    }
    }

    @keyframes wave-md {
    0% {
        opacity: 0.35;
        height: 30px;
    }
    100% {
        opacity: 1;
        height: 75px;
    }
    }

    @keyframes wave-lg {
    0% {
        opacity: 0.35;
        height: 30px;
    }
    100% {
        opacity: 1;
        height: 100px;
    }
    }

.anim-scroll--wheel {
    animation: scroll 2.5s ease infinite;
    background: #fff;
    border-radius: 30px;
    height: 8px;
    left: calc(50% - 1.5px);
    position: absolute;
    right: 50%;
    top: 5px;
    width: 3px;
    }
    @keyframes scroll {
    0% {
        transform: translateY(0);
    }
    50% {
        transform: translateY(16px);
    }
    51% {
        opacity: 1;
    }
    100% {
        opacity: 0;
        transform: translateY(0);
    }
    }
</style>