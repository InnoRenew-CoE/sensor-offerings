<script lang="ts">
    import Navigation from "$lib/Navigation.svelte";
    import SensorCard from "$lib/SensorCard.svelte";
    import { fade } from "svelte/transition";

    let scrollY = $state(0);
</script>

<svelte:window bind:scrollY />
<Navigation />
{#if scrollY >= 100}
    <div class="hidden sm:block sm:sticky cursor-pointer top-24 w-min m-auto text-nowrap z-50" onclick={() => (scrollY = 0)} in:fade out:fade>
        <div class="backdrop-blur bg-black/85 hadow-lg rounded-full text-white flex items-center justify-center py-1 px-5">Scroll to top</div>
    </div>
{/if}
<div class="-mt-25 p-10 sm:p-30 py-40 bg-white" id="home">
    <div class="text-2xl text-indigo-500 font-departure">Sensors for Building Monitoring</div>
    <p class="text-lg w-full sm:w-[80%] py-10 px-5 text-gray-700">
        Monitor your building like never before. Our service connects a variety of sensor vailable directly from our sit nd integrates seamlessly with a powerful data store, giving you real-time insights and actionable data to optimize building performance.
    </p>

    <div class="border-dashed h-0.5 border-primary/50 border"></div>
    <div class="grid gap-5 py-5 font-departure items-center justify-center">
        <a target="_blank" href="https://innorenew.eu" class="grid gap-5 text-center">
            <div class="flex items-center justify-center w-[90%] max-w-[300px]">
                <img src="logo.png" alt="logo-innorenew" class="w-full" />
            </div>
            <div>Built by InnoRenew CoE</div>
        </a>
    </div>
</div>
<div class="flex items-center justify-center">
    <div class="w-full flex flex-col gap-5 items-center justify-center">
        <!-- IAQ -->
        <div class="w-full">
            <div class="py-5 grid gap-5 bg-[#213448] w-full">
                <span id="iaq" class="text-white font-departure text-xl text-left m-auto w-[90%] pt-24">Indoor Air Quality sensor</span>
                <div class="m-auto w-[80%] flex items-center justify-center">
                    <SensorCard fileLeft="iaq-transparent.png" fileRight="iaq.png" class="rounded-xl ">
                        <div class=" h-full p-3 text-white flex flex-wrap gap-5">
                            <div>
                                <span class="font-departure text-[#fff]">Supported Indicators:</span>
                                <ul class="list-disc pl-8 pt-3 space-y-1 text-white">
                                    <li>Carbon dioxide (CO₂)</li>
                                    <li>Volatile organic compounds (VOC)</li>
                                    <li>Nitric Oxide (NOx)</li>
                                    <li>Formaldehyde (HCHO)</li>
                                    <li>Particulate Matter (PM1, PM2.5, PM4, PM10)</li>
                                    <li>Temperature</li>
                                    <li>Humidity</li>
                                    <li>Luminance</li>
                                </ul>
                            </div>
                            <div>
                                <span class="font-departure text-[#fff]">Short Description:</span>
                                <div class="p-2">State-of-the-art wireless sensor measuring key indoor environmental factors. Powered by high-precision Sensirion sensors, it helps study how air quality affects health, comfort, and productivity, especially in workplaces.</div>
                            </div>
                        </div>
                    </SensorCard>
                </div>
            </div>

            <div class="p-6 min-h-[30vh] w-[80%] m-auto">
                <span class="font-departure text-primary text-xl">Why pick iaq?</span>
                <div class="mx-auto bg-white rounded-xl">
                    <h2 class="text-2xl font-bold mb-4">Indoor Air Quality (IAQ) Sensor</h2>

                    <p class="text-slate-700 leading-relaxed mb-4">
                        Our Indoor Air Quality (IAQ) sensor is a state-of-the-art wireless device designed to monitor and analyze key environmental parameters that impact health, comfort, and productivity in indoor spaces. Equipped with high- precision sensors from Sensirion, a leading manufacturer
                        of quality surface-mount devices (SMD). It is an invaluable tool for research into the dynamics of indoor air quality, particularly in working environments, where it helps assess the relationship between air quality and employee health and performance.
                    </p>

                    <p class="text-slate-700 leading-relaxed mb-4">
                        Additionally, it plays a critical role in studying the impact of modern building material specially renewable and sustainable materials like woo n indoor air quality, making it ideal for new wooden public buildings and research institutes experimenting with innovative
                        construction materials. While our primary clients include public institutions and research facilities, the sensor is also well-suited for private homes seeking to optimize indoor environments.
                    </p>

                    <p class="text-slate-700 leading-relaxed mb-6">By providing precise, real-time data, our IAQ sensor empowers clients to make informed decisions that enhance indoor air quality, promote well-being, and support sustainable building practices.</p>
                </div>
            </div>
        </div>

        <!-- Sound -->
        <div class="w-full">
            <div class="py-5 grid gap-5 bg-[#070F2B] w-full">
                <span id="sound" class="text-white m-auto font-departure text-xl text-left w-[90%] pt-24">Sound sensor</span>
                <div class="m-auto w-[80%] flex items-center justify-center">
                    <SensorCard fileLeft="sound-transparent.png" fileRight="sound.png" class="rounded-xl ">
                        <div class=" h-full p-3 text-white flex flex-wrap">
                            <div>
                                <span class="font-departure text-[#fff]">Best for:</span>
                                <ul class="list-disc pl-6 space-y-2 pt-2">
                                    <li>Workplace noise monitoring to study stress and productivity</li>
                                    <li>Urban noise measurement for concerts, events, and city planning</li>
                                    <li>Indoor environmental research on sound exposure</li>
                                    <li>Privacy-conscious noise monitoring with on-device AI classification</li>
                                </ul>
                            </div>
                            <div>
                                <span class="font-departure text-[#fff]">Description:</span>
                                <div class="p-3">Wireless sensors measuring indoor/outdoor noise. One tracks decibels, the other adds on-device AI audio classification with privacy. Useful for workplace studies and urban noise monitoring.</div>
                            </div>
                        </div>
                    </SensorCard>
                </div>
            </div>

            <div class="p-6 min-h-[30vh] w-[80%] m-auto">
                <span class="font-departure text-primary text-xl">Why pick SPL?</span>
                <div class="mx-auto bg-white rounded-xl">
                    <h2 class="text-2xl font-bold mb-4">Sound Pressure Level (SPL) Sensors</h2>

                    <p class="text-slate-700 leading-relaxed mb-4">
                        Our Sound Pressure Level (SPL) sensors are advanced, calibrated devices designed to measure and analyze noise levels in both indoor and outdoor environments. Available in two variants, these wireless sensors cater to a wide range of applications.
                    </p>

                    <p class="text-slate-700 leading-relaxed mb-4">
                        The first variant measures decibel levels alone, providing precise noise monitoring where sound pressure is the primary concern. The second includes an omnidirectional microphone that activates above 80 dB, capturing audio recordings processed on the device. Using Fast
                        Fourier Transform (FFT), recordings are converted into a frequency spectrum for AI-driven noise source classification. Privacy is ensure ecordings never leave the device and are destroyed after classification.
                    </p>

                    <p class="text-slate-700 leading-relaxed mb-4">
                        Indoors, SPL sensors help study workplace environments and their impact on stress and productivity. Outdoors, they monitor urban noise during events like concerts, helping cities mitigate negative effects on residents. With customizable casings for indoor and outdoor use,
                        these sensors offer a versatile, privacy-conscious solution for noise monitoring and analysis.
                    </p>
                </div>
            </div>
        </div>

        <!-- Outdoor Sound -->
        <div class="w-full">
            <div class="py-5 grid gap-5 bg-[#1E201E] w-full">
                <span id="outdoor" class="text-white m-auto font-departure text-xl text-left w-[90%] pt-24">Outdoor Sound sensor</span>
                <div class="m-auto w-[80%] flex items-center justify-center">
                    <SensorCard fileLeft="swarm-transparent.png" fileRight="swarm.png" class="rounded-xl ">
                        <div class=" h-full p-3 text-white flex flex-wrap lg:grid">
                            <div>
                                <span class="font-departure text-[#fff]">Best for:</span>
                                <ul class="list-disc pl-8 pt-3 space-y-1 text-white">
                                    <ul class="list-disc list-inside mt-1">
                                        <li>Privacy-preserving sound classification</li>
                                        <li>Smart event monitoring</li>
                                        <li>Urban planning and noise mapping</li>
                                        <li>Identifying noise sources (music, crowds, traffic, etc.)</li>
                                        <li>Threshold-based alerts without storing audio</li>
                                    </ul>
                                </ul>
                            </div>
                            <div>
                                <span class="font-departure text-[#fff]">Description:</span>
                                <div class="p-3">
                                    A dual-microphone Sound Sensor for contextual noise monitoring. When noise levels change, on-device Edge AI instantly classifies sources like machinery, music, or voices. All audio is processed locally and deleted immediately, providing actionable insight without
                                    retaining data.
                                </div>
                            </div>
                        </div>
                    </SensorCard>
                </div>
            </div>

            <div class="p-6 min-h-[30vh] w-[80%] m-auto">
                <span class="font-departure text-primary text-xl">Why pick outdoor SPL?</span>
                <div class="mx-auto bg-white rounded-xl">
                    Outdoor SPL provides accurate, real-world sound pressure data that reflects the true acoustic conditions of an environment. By capturing noise exactly where it occurs, it becomes an essential foundation for understanding environmental impact, assessing compliance, and improving
                    long-term planning.
                    <br />
                    <br />
                    When paired with our Edge AI classification pipeline, Outdoor SPL doesn’t just tell you how loud something was it helps reveal what caused it.
                    <br />
                    <br />
                    Whether it’s traffic flow, construction machinery, or large crowd activity, you gain contextual insight that transforms raw decibel readings into actionable intelligence for cities, venues, and operational teams.
                </div>
            </div>
        </div>

        <!-- MHT -->
        <div class="w-full">
            <div class="py-5 grid gap-5 bg-[#35374B] w-full">
                <span id="mht" class="m-auto text-white font-departure text-xl text-left w-[90%] pt-24">Wood Moisture Content sensor</span>
                <div class="m-auto w-[80%] flex items-center justify-center">
                    <SensorCard fileLeft="mht-transparent.png" fileRight="mht.png" class="rounded-xl ">
                        <div class=" h-full p-3 text-white flex flex-wrap">
                            <div>
                                <span class="font-departure">Best for:</span>
                                <ul class="list-disc pl-6 space-y-1 pt-1">
                                    <li>Monitoring moisture levels in timber constructions</li>
                                    <li>Preventing mold, rot, and structural damage in wooden buildings</li>
                                    <li>Research on sustainable and innovative building materials</li>
                                    <li>Ensuring long-term durability and performance of timber structures</li>
                                </ul>
                            </div>

                            <div>
                                <span class="font-departure">Description:</span>
                                <div class="p-3">Sensors installed directly in timber to track moisture levels, combined with ambient RH/T sensors. They help prevent mold, rot, and structural issues, supporting timber construction and sustainable building research.</div>
                            </div>
                        </div>
                    </SensorCard>
                </div>
            </div>

            <div class="p-6 min-h-[30vh] w-[80%] m-auto">
                <span class="font-departure text-primary text-xl">Why pick MC?</span>
                <div class="mx-auto bg-white rounded-xl">
                    <h2 class="text-2xl font-bold mb-4">Moisture Content (MC) Sensors</h2>

                    <p class="text-slate-700 leading-relaxed mb-4">
                        Our Moisture Content (MC) sensors are specialized devices designed to provide critical insights into the moisture dynamics within timber constructions, ensuring the longevity and structural integrity of wooden buildings. These sensors support both wired and wireless
                        communication, with wired being preferred due to limited access after installation.
                    </p>

                    <p class="text-slate-700 leading-relaxed mb-4">
                        Installed directly into the wood by screwing them into the material, the sensors measure moisture inside the timber itsel ffering far more relevant data than standard relative humidity (RH) and temperature (T) sensors alone. To achieve comprehensive monitoring, we typically
                        install these sensors within the building envelope, complemented by three additional RH/T sensors that track surrounding air conditions.
                    </p>

                    <p class="text-slate-700 leading-relaxed mb-6">
                        This dual-layer system helps analyze the interaction between wood moisture and ambient humidity, providing essential data for preventing mold, rot, and structural degradation. Ideal for timber buildings and research on sustainable materials, our MC sensors support architects,
                        builders, and researchers in improving durability and performance.
                    </p>
                </div>
            </div>
        </div>

        <!-- Grafana -->
        <div class="w-full">
            <div class="py-5 grid gap-5 bg-[#0F0E0E] w-full text-white">
                <span id="grafana" class=" font-departure text-xl text-left m-auto w-[90%] pt-24">Data Visualisation - Grafana Dashboard</span>
                <div class="m-auto w-[80%] flex items-center justify-center">
                    <SensorCard fileLeft="grafana-test.png" fileRight="sketch.svg" class="shadow bg-white rounded-xl " rightClass="object-contain">
                        <div class=" h-full p-3 flex flex-wrap">
                            <div>
                                <span class="font-departure">Data export:</span>
                                <ul class="list-disc pl-8 pt-3 space-y-1">
                                    <li>CSV</li>
                                    <li>JSON</li>
                                </ul>
                            </div>

                            <div>
                                <span class="font-departure">Short Description:</span>
                                <div class="p-2">
                                    All sensors work with the software system, which combines open-source and custom solutions, using a high-performance time-series database for fast, interval-based queries.
                                    <div class="border border-green-600/85 bg-green-600/10 w-min py-1 px-2 text-nowrap rounded-full text-sm text-green-600">Open Source</div>
                                </div>
                            </div>
                        </div>
                    </SensorCard>
                </div>
            </div>
            <div class="p-6 min-h-[30vh] w-[80%] m-auto">
                <span class="font-departure text-primary text-xl">Why the dashboard?</span>
                <div class="mx-auto p-6 bg-white rounded-xl">
                    <h2 class="text-2xl font-bold mb-4">Software Integration</h2>

                    <p class="text-slate-700 leading-relaxed mb-4">All sensors integrate with the provided software system, a robust combination of open-source solutions and custom code. A high-performance time-series database stores measurements and supports fast interval-based queries.</p>

                    <p class="text-slate-700 leading-relaxed mb-4">
                        For visualizations, Grafana renders graphical dashboards of the building’s state. The software supports multiple users, permission schemes, a custom alert system (email or popular IM services), and custom floor plan visualizations based on architect-provided layouts.
                    </p>

                    <p class="text-slate-700 leading-relaxed">For advanced analysis, data can be exported at any time interval in standard formats such as CSV and JSON.</p>
                </div>
            </div>
        </div>
    </div>
</div>
<footer class="bg-white p-5 grid gap-5 items-center justify-center font-departure">
    <a target="_blank" href="https://innorenew.eu" class="grid gap-5 text-center">
        <div class="flex items-center justify-center w-[90%] max-w-[300px]">
            <img src="logo.png" alt="logo-innorenew" class="w-full" />
        </div>
        <div>Built by InnoRenew CoE</div>
    </a>
</footer>
