<script lang="ts">
    import { onMount } from "svelte";
    import SvgIcon from "./SvgIcon.svelte";

    let element: HTMLDivElement | undefined = $state(undefined);

    onMount(() => {
        if (element) {
            const div = element;
            div.scrollLeft = 300;
            setTimeout(() => {
                div.scrollLeft = 0;
            }, 1500);
        }
    });
</script>

<header class="flex gap-3 items-stretch justify-center sm:py-5 sticky top-0 left-0 right-0 z-50 text-nowrap whitespace-nowrap">
    <div class="flex sm:items-stretch gap-3 w-full sm:w-fit text-white p-2 px-3 sm:rounded-full bg-black sm:bg-black/85 backdrop-blur-lg border border-white/20 shadow-xl">
        <div bind:this={element} class="scroll-smooth no-scrollbar transition-all flex gap-0.5 items-center overflow-scroll">
            <a href="#iaq" class="bg-white/10 hover:bg-white/20 px-4 py-1 rounded-full sm:rounded-none sm:rounded-l-full cursor-pointer transition-all duration-200 font-medium">Indoor Air Quality</a>
            <a href="#sound" class="bg-white/10 hover:bg-white/20 px-4 py-1 rounded-full sm:rounded-none cursor-pointer transition-all duration-200 font-medium">Sound sensors</a>
            <a href="#mht" class="bg-white/10 hover:bg-white/20 px-4 py-1 cursor-pointer transition-all duration-200 font-medium rounded-full sm:rounded-none">Wood sensors</a>
            <a href="#grafana" class="bg-white/10 hover:bg-white/20 px-4 py-1 rounded-full sm:rounded-none sm:rounded-r-full cursor-pointer transition-all duration-200 font-medium">Visualisation</a>
        </div>

        <div class="flex items-start sm:items-center">
            <a href="mailto:coe@innorenew.eu" class="flex gap-3 items-center bg-primary rounded-full py-1 px-3">
                <SvgIcon src="./contact.svg" class="bg-white size-4" />
                Contact
            </a>
        </div>
    </div>
</header>
