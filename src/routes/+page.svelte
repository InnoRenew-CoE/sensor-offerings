<script lang="ts">
    import SensorCard from "$lib/SensorCard.svelte";
    import SvgIcon from "$lib/SvgIcon.svelte";
    import { fly } from "svelte/transition";
    let hoveringLogo = $state(false);
</script>

<header class="flex gap-3 items-stretch justify-center py-5 sticky top-0 left-0 right-0 z-50 text-nowrap whitespace-nowrap">
    <a target="_blank" href="https://innorenew.eu">
        <div class="flex gap-5 items-center" onmouseenter={() => (hoveringLogo = true)} onmouseleave={() => (hoveringLogo = false)}>
            <div class="p-1 bg-primary/30 backdrop-blur-2xl rounded-full size-11">
                <img src="logo.svg" alt="logo-innorenew" class="w-full" />
            </div>
            {#if hoveringLogo}
                <div in:fly class="flex gap-2 font-departure text-xs text-indigo-500">
                    <SvgIcon src="./link.svg" class="bg-indigo-500 size-4" />
                    by InnoRenew
                </div>
            {/if}
        </div>
    </a>
    <div class="w-fit text-white flex items-center p-1 rounded-full bg-black/85 backdrop-blur-lg border border-white/20 shadow-lg">
        <ul class="flex gap-0.5">
            <a href="#iaq" class="bg-white/10 hover:bg-white/20 px-4 py-1 rounded-l-full cursor-pointer transition-all duration-200 font-medium">Indoor Air Quality</a>
            <a href="#sound" class="bg-white/10 hover:bg-white/20 px-4 py-1 cursor-pointer transition-all duration-200 font-medium">Sound sensors</a>
            <a href="#mht" class="bg-white/10 hover:bg-white/20 px-4 py-1 rounded-r-full cursor-pointer transition-all duration-200 font-medium">Wood sensors</a>
        </ul>
    </div>
    <div class="flex items-center text-white bg-primary/80 backdrop-blur-2xl rounded-full w-min hover:bg-black/50">
        <a href="mailto:aleksandar.tosic@innorenew.eu" class="flex items-center gap-3 px-4 py-2 rounded-r-full cursor-pointer transition-all duration-200 font-medium">
            <SvgIcon src="./contact.svg" class="bg-white size-4" />
            Contact
        </a>
    </div>
</header>
<div class="-mt-25 p-10 py-40 bg-white">
    <div class="text-2xl text-indigo-500">Yada Yada helth build</div>
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatibus perferendis velit aliquid perspiciatis itaque dolor consequatur exercitationem ullam rerum nemo iusto praesentium nobis, id temporibus, molestias saepe similique incidunt mollitia?
    <br />Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatibus perferendis velit aliquid perspiciatis itaque dolor consequatur exercitationem ullam rerum nemo iusto praesentium nobis, id temporibus, molestias saepe similique incidunt mollitia?
    <br />Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatibus perferendis velit aliquid perspiciatis itaque dolor consequatur exercitationem ullam rerum nemo iusto praesentium nobis, id temporibus, molestias saepe similique incidunt mollitia?
    <div class="py-5">
        <div class="h-0.5 bg-primary"></div>
    </div>
    <div class="text-2xl text-primary font-departure text-center">Wimpity wompity get me the text</div>
</div>
<div class="flex items-center justify-center">
    <div class="w-full flex flex-col gap-5 items-center justify-center">
        <span id="iaq" class="font-departure text-xl text-left w-[90%] pt-7.5">Indoor Air Quality sensor</span>
        <div class="py-5 grid gap-5 bg-black w-full">
            <div class="m-auto w-[80%] flex items-center justify-center">
                <SensorCard file="iaq" class="rounded-xl">
                    <div class=" h-full p-3 text-white">
                        <span class="font-departure text-[#8CE4FF]">Best for:</span>
                        <ul class="list-disc pl-10">
                            <li>a</li>
                            <li>b</li>
                            <li>c</li>
                            <li>d</li>
                        </ul>
                        <br />
                        <span class="font-departure text-[#8CE4FF]">Description:</span>
                        <div class="p-3">Lorem ipsum dolor sit amet consectetur adipisicing elit. Quos adipisci accusantium delectus ipsum minima illum recusandae, cupiditate repudiandae! Odio neque provident animi incidunt commodi tempore, minus molestiae est nam quidem.</div>
                    </div>
                </SensorCard>
            </div>
        </div>

        <div class="pb-20 min-h-[30vh]">
            <span class="font-departure text-primary text-xl">Yada yada why pick iaq?</span>
            <div>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Autem quo iusto nobis, perspiciatis incidunt maiores recusandae hic ab omnis exercitationem praesentium corrupti minima laudantium voluptatem officia sequi eveniet architecto numquam?</div>
        </div>

        <span id="sound" class="font-departure text-xl text-left w-[90%] pt-7.5">Sound sensor</span>
        <div class="py-5 grid gap-5 bg-black w-full">
            <div class="m-auto w-[80%] flex items-center justify-center">
                <SensorCard file="sound" class="rounded-xl">
                    <div class=" h-full p-3 text-white">
                        <span class="font-departure text-[#8CE4FF]">Best for:</span>
                        <ul class="list-disc pl-10">
                            <li>a</li>
                            <li>b</li>
                            <li>c</li>
                            <li>d</li>
                        </ul>
                        <br />
                        <span class="font-departure text-[#8CE4FF]">Description:</span>
                        <div class="p-3">Lorem ipsum dolor sit amet consectetur adipisicing elit. Quos adipisci accusantium delectus ipsum minima illum recusandae, cupiditate repudiandae! Odio neque provident animi incidunt commodi tempore, minus molestiae est nam quidem.</div>
                    </div>
                </SensorCard>
            </div>
        </div>

        <div class="pb-20 min-h-[30vh]">
            <span class="font-departure text-primary text-xl">Yada yada why pick Sound?</span>
            <div>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Autem quo iusto nobis, perspiciatis incidunt maiores recusandae hic ab omnis exercitationem praesentium corrupti minima laudantium voluptatem officia sequi eveniet architecto numquam?</div>
        </div>

        <span id="mht" class="font-departure text-xl text-left w-[90%] pt-7.5">Wood Moisture Content sensor</span>
        <div class="py-5 grid gap-5 bg-black w-full">
            <div class="m-auto w-[80%] flex items-center justify-center">
                <SensorCard file="mht" class="rounded-xl">
                    <div class=" h-full p-3 text-white">
                        <span class="font-departure text-[#8CE4FF]">Best for:</span>
                        <ul class="list-disc pl-10">
                            <li>a</li>
                            <li>b</li>
                            <li>c</li>
                            <li>d</li>
                        </ul>
                        <br />
                        <span class="font-departure text-[#8CE4FF]">Description:</span>
                        <div class="p-3">Lorem ipsum dolor sit amet consectetur adipisicing elit. Quos adipisci accusantium delectus ipsum minima illum recusandae, cupiditate repudiandae! Odio neque provident animi incidunt commodi tempore, minus molestiae est nam quidem.</div>
                    </div>
                </SensorCard>
            </div>
        </div>

        <div class="pb-20 min-h-[30vh]">
            <span class="font-departure text-primary text-xl">Yada yada why pick mht?</span>
            <div>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Autem quo iusto nobis, perspiciatis incidunt maiores recusandae hic ab omnis exercitationem praesentium corrupti minima laudantium voluptatem officia sequi eveniet architecto numquam?</div>
        </div>
    </div>
</div>
<footer class="bg-black p-10 text-white">
    fuck u
    <div>Built by InnoRenew CoE</div>
</footer>
