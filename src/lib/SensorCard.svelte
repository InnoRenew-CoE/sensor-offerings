<script lang="ts">
    import { onMount } from "svelte";
    import { twMerge } from "tailwind-merge";

    let sliderPosition = $state(50);
    let isDragging = false;
    let containerRef: HTMLDivElement;
    const { fileLeft, fileRight, class: className }: { fileLeft: string; fileRight: string; class: string } = $props();

    function handleMove(clientX: number) {
        console.log("move");
        if (!containerRef || !isDragging) return;
        const rect = containerRef.getBoundingClientRect();
        const x = clientX - rect.left;
        const percentage = (x / rect.width) * 100;
        sliderPosition = Math.min(Math.max(percentage, 0), 100);
    }

    function handleMouseDown() {
        isDragging = true;
    }

    function handleMouseMove(e: MouseEvent) {
        if (!isDragging) return;
        handleMove(e.clientX);
    }

    function handleMouseUp() {
        isDragging = false;
    }

    function handleTouchMove(e: TouchEvent) {
        if (e.touches.length > 0) {
            handleMove(e.touches[0].clientX);
        }
    }

    onMount(async () => {
        setTimeout(() => (sliderPosition = 75), 500);
        setTimeout(() => (sliderPosition = 25), 1500);
        setTimeout(() => (sliderPosition = 50), 2500);
    });
</script>

<div class="flex w-full gap-5 relative flex-wrap lg:flex-nowrap">
    <div class={twMerge("w-full overflow-hidden", className)} on:mousemove={handleMouseMove} on:mouseup={handleMouseUp} on:touchend={handleMouseUp}>
        <div bind:this={containerRef} class="group relative w-full aspect-video select-none" on:mousedown={handleMouseDown} on:touchstart={handleMouseDown} on:touchmove={handleTouchMove}>
            <div class="transition-all duration-500 group-hover:transition-none absolute inset-0">
                <img src="./photos/{fileRight}" alt="After" class="h-full w-full object-cover" />
            </div>

            <div class="transition-all duration-500 group-hover:transition-none absolute inset-0" style="clip-path: inset(0 {100 - sliderPosition}% 0 0);">
                <img src="./photos/{fileLeft}   " alt="After" class="w-full h-full object-cover" />
            </div>

            <div class="transition-all duration-500 group-hover:transition-none absolute top-0 bottom-0 w-1 bg-white" style="left: {sliderPosition}%;">
                <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-12 h-12 bg-white rounded-full shadow-lg flex items-center justify-center">
                    <svg width="70%" height="100%" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path d="M9 7L4 12L9 17M15 7L20 12L15 17" stroke="currentColor" stroke-width="1" stroke-linecap="round" stroke-linejoin="round" />
                    </svg>
                </div>
            </div>
        </div>
    </div>
    <div class="lg:w-[40%]">
        <slot />
    </div>
</div>
