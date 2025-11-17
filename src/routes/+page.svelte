<script>
    import SensorCard from "$lib/SensorCard.svelte";
</script>

<div class="text-2xl font-bold">Our Offerings bla bla</div>
<div class="flex items-center justify-center">
    <div class="w-full grid gap-5">
        <div class="flex items-center justify-center">
            <div class="w-[50%] grid gap-5">
                <div class="">
                    <SensorCard file="iaq" class="shadow-sm border border-white rounded-xl">
                        <div class="rounded-lg shadow-sm h-full p-3 border border-white">
                            <span>Indoor Air Quality sensor</span>
                        </div>
                    </SensorCard>
                </div>
                <div class="">
                    <SensorCard file="sound" class="shadow-sm border border-white rounded-xl">
                        <div class="rounded-lg shadow-sm h-full p-3 border border-white">
                            <span>Sound sensor</span>
                        </div>
                    </SensorCard>
                </div>
                <div class="">
                    <SensorCard file="mht" class="shadow-sm border border-white rounded-xl">
                        <div class="rounded-lg shadow-sm h-full p-3 border border-white">
                            <span>Sound sensor</span>
                        </div>
                    </SensorCard>
                </div>
            </div>
        </div>
    </div>
</div>
