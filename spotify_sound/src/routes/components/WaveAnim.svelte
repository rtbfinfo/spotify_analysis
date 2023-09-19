<script lang="ts">
    import { fade,slide } from "svelte/transition";
    export let currentStep: number;

    $: console.log(plusCourt)
    let intro = true;
    let plusCourt = true;

    $: if (currentStep == 2) {
        intro = false;
    } else if (currentStep < 2) {
        intro = true;
    }

    $: if (currentStep == 3) {
        plusCourt = false;
    } else if (currentStep < 3) {
        plusCourt = true;
    }
</script>

<div transition:slide|local class="bg-cardBg rounded-lg gap-0 p-4 flex flex-col w-full md:w-96 justify-center items-center  hover:opacity-90 {currentStep == 1 || currentStep == 2 || currentStep == 3 ? "opacity-100" : "opacity-50 transition-all duration-500"}">
    <svg width="337" height="98" viewBox="0 0 337 98" fill="none" xmlns="http://www.w3.org/2000/svg">
        {#if intro}
        <g transition:fade>
            <rect y="41" width="5" height="16" rx="2.5" fill="#FF365E"/>
            <rect x="8.86108" y="35" width="6" height="28" rx="3" fill="#FF365E"/>
        </g>
        {/if}
        <rect x="18.7222" y="30" width="6" height="38" rx="3" fill="#FF365E"/>
        <rect x="28.5833" y="33" width="5" height="32" rx="2.5" fill="#FF365E"/>
        <rect x="37.4443" y="27.5" width="5" height="43" rx="2.5" fill="#04BE8C"/>
        <rect x="46.3054" y="17.5" width="5" height="63" rx="2.5" fill="#04BE8C"/>
        <rect x="55.1665" y="5" width="5" height="88" rx="2.5" fill="#04BE8C"/>
        <rect x="64.0276" y="19.5" width="6" height="59" rx="3" fill="#04BE8C"/>
        <rect x="73.8887" y="29" width="6" height="40" rx="3" fill="#04BE8C"/>
        <rect x="83.7499" y="15.5" width="5" height="67" rx="2.5" fill="#04BE8C"/>
        <rect x="92.6111" y="11" width="5" height="76" rx="2.5" fill="#04BE8C"/>
        <rect x="101.472" y="15" width="5" height="68" rx="2.5" fill="#04BE8C"/>
        <rect x="110.333" width="6" height="98" rx="3" fill="#04BE8C"/>
        <rect x="120.194" y="11" width="6" height="76" rx="3" fill="#04BE8C"/>
        <rect x="130.056" y="22" width="5" height="54" rx="2.5" fill="#04BE8C"/>
        <rect x="138.917" y="27" width="5" height="44" rx="2.5" fill="#04BE8C"/>
        <rect x="147.778" y="19" width="5" height="60" rx="2.5" fill="#04BE8C"/>
        <rect x="156.639" y="29" width="5" height="40" rx="2.5" fill="#04BE8C"/>
        <rect x="165.5" y="20" width="6" height="58" rx="3" fill="#04BE8C"/>
        <rect x="175.361" y="8.5" width="5" height="81" rx="2.5" fill="#04BE8C"/>
        <rect x="184.222" y="13" width="5" height="72" rx="2.5" fill="#04BE8C"/>
        <rect x="193.083" y="23" width="5" height="52" rx="2.5" fill="#04BE8C"/>
        <rect x="201.944" y="11" width="5" height="76" rx="2.5" fill="#04BE8C"/>
        <rect x="210.806" y="15" width="6" height="68" rx="3" fill="#04BE8C"/>
        <rect x="220.667" width="6" height="98" rx="3" fill="#04BE8C"/>
        <rect x="230.528" y="11" width="5" height="76" rx="2.5" fill="#04BE8C"/>
        <rect x="239.389" y="22" width="5" height="54" rx="2.5" fill="#04BE8C"/>
        {#if plusCourt}
        <g transition:fade>
            <rect x="248.25" y="31" width="5" height="36" rx="2.5" fill="#04BE8C"/>
            <rect x="257.111" y="26" width="6" height="46" rx="3" fill="#04BE8C"/>
            <rect x="266.972" y="32" width="6" height="34" rx="3" fill="#04BE8C"/>
            <rect x="276.833" y="26" width="5" height="46" rx="2.5" fill="#04BE8C"/>
            <rect x="285.694" y="21" width="5" height="56" rx="2.5" fill="#04BE8C"/>
            <rect x="294.556" y="11" width="5" height="76" rx="2.5" fill="#04BE8C"/>
            <rect x="303.417" y="15" width="5" height="68" rx="2.5" fill="#04BE8C"/>
            <rect x="312.278" width="6" height="98" rx="3" fill="#04BE8C"/>
            <rect x="322.139" y="11" width="6" height="76" rx="3" fill="#04BE8C"/>
            <rect x="332" y="22" width="5" height="54" rx="2.5" fill="#04BE8C"/>
        </g>
        {/if}
        </svg>
        
</div>