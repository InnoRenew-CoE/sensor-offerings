<script lang="ts">
    import Navigation from "$lib/Navigation.svelte";
    import SensorCard from "$lib/SensorCard.svelte";
    import { fade } from "svelte/transition";

    let scrollY = $state(0);
</script>

<svelte:window bind:scrollY />
<Navigation language="si" />
{#if scrollY >= 100}
    <div class="hidden sm:block sm:sticky cursor-pointer top-24 w-min m-auto text-nowrap z-50" onclick={() => (scrollY = 0)} in:fade out:fade>
        <div class="backdrop-blur bg-black/85 hadow-lg rounded-full text-white flex items-center justify-center py-1 px-5">Pomakni na vrh</div>
    </div>
{/if}
<div class="-mt-25 p-10 sm:p-30 py-40 bg-white" id="home">
    <div class="text-2xl text-indigo-500 font-departure">Senzorji za nadzor stavb</div>
    <p class="text-lg w-full sm:w-[80%] py-10 px-5 text-gray-700">
        Spremljajte svojo stavbo kot še nikoli. Naša storitev povezuje različne senzorje, ki so na voljo neposredno z našega spletnega mesta, in se brezhibno integrira z zmogljivo shrambo podatkov, kar vam zagotavlja vpoglede v realnem času in uporabne podatke za optimizacijo delovanja stavbe.
    </p>

    <div class="border-dashed h-0.5 border-primary/50 border"></div>
    <div class="grid gap-5 py-5 font-departure items-center justify-center">
        <a target="_blank" href="https://innorenew.eu" class="grid gap-5 text-center">
            <div class="flex items-center justify-center w-[90%] max-w-[300px]">
                <img src="logo.png" alt="logo-innorenew" class="w-full" />
            </div>
            <div>Izdelal InnoRenew CoE</div>
        </a>
    </div>
</div>
<div class="flex items-center justify-center">
    <div class="w-full flex flex-col gap-5 items-center justify-center">
        <!-- IAQ -->
        <div class="w-full">
            <div class="py-5 grid gap-5 bg-[#213448] w-full">
                <span id="iaq" class="text-white font-departure text-xl text-left m-auto w-[90%] pt-24"> </span>
                <div class="m-auto w-[80%] flex items-center justify-center">
                    <SensorCard fileLeft="iaq-transparent.png" fileRight="iaq.png" class="rounded-xl ">
                        <div class=" h-full p-3 text-white flex flex-wrap gap-5">
                            <div>
                                <span class="font-departure text-[#fff]">Podprti kazalniki:</span>
                                <ul class="list-disc pl-8 pt-3 space-y-1 text-white">
                                    <li>Ogljikov dioksid (CO₂)</li>
                                    <li>Hlapne organske spojine (VOC)</li>
                                    <li>Dušikov oksid (NOx)</li>
                                    <li>Formaldehid (HCHO)</li>
                                    <li>Trdni delci (PM1, PM2.5, PM4, PM10)</li>
                                    <li>Temperatura</li>
                                    <li>Vlaga</li>
                                    <li>Osvetlitev</li>
                                </ul>
                            </div>
                            <div>
                                <span class="font-departure text-[#fff]">Kratek opis:</span>
                                <div class="p-2">Najsodobnejši brezžični senzor, ki meri ključne dejavnike notranjega okolja. Uporablja natančne senzorje Sensirion in pomaga preučevati, kako kakovost zraka vpliva na zdravje, udobje in produktivnost, zlasti na delovnih mestih.</div>
                            </div>
                        </div>
                    </SensorCard>
                </div>
            </div>

            <div class="p-6 min-h-[30vh] w-[80%] m-auto">
                <span class="font-departure text-primary text-xl">Zakaj izbrati nadzor zraka v notranjih prostorih (IAQ)?</span>
                <div class="mx-auto bg-white rounded-xl">
                    <h2 class="text-2xl font-bold mb-4">Senzor kakovosti zraka v zaprtih prostorih (IAQ)</h2>

                    <p class="text-slate-700 leading-relaxed mb-4">
                        Naš senzor kakovosti zraka v zaprtih prostorih (IAQ) je najsodobnejša brezžična naprava, zasnovana za spremljanje in analizo ključnih okoljskih parametrov, ki vplivajo na zdravje, udobje in produktivnost v zaprtih prostorih. Uporablja natančne senzorje podjetja Sensirion,
                        vodilnega proizvajalca visoko kakovostnih SMD naprav. Je neprecenljivo orodje za raziskave dinamike kakovosti zraka v zaprtih prostorih, zlasti v delovnih okoljih.
                    </p>

                    <p class="text-slate-700 leading-relaxed mb-4">
                        Poleg tega igra ključno vlogo pri preučevanju vpliva sodobnih gradbenih materialov – zlasti obnovljivih in trajnostnih, kot je les – na kakovost zraka v notranjih prostorih, zaradi česar je idealen za nove lesene javne stavbe in raziskovalne inštitute, ki eksperimentirajo z
                        inovativnimi materiali.
                    </p>

                    <p class="text-slate-700 leading-relaxed mb-6">Z zagotavljanjem natančnih podatkov v realnem času senzor uporabnikom omogoča sprejemanje premišljenih odločitev, izboljševanje kakovosti zraka, povečanje dobrega počutja ter podporo trajnostnim gradbenim praksam.</p>
                </div>
            </div>
        </div>

        <!-- Sound -->
        <div class="w-full">
            <div class="py-5 grid gap-5 bg-[#070F2B] w-full">
                <span id="sound" class="text-white m-auto font-departure text-xl text-left w-[90%] pt-24">Zvočni senzor</span>
                <div class="m-auto w-[80%] flex items-center justify-center">
                    <SensorCard fileLeft="sound-transparent.png" fileRight="sound.png" class="rounded-xl ">
                        <div class=" h-full p-3 text-white flex flex-wrap">
                            <div>
                                <span class="font-departure text-[#fff]">Najboljše za:</span>
                                <ul class="list-disc pl-6 space-y-2 pt-2">
                                    <li>Spremljanje hrupa na delovnem mestu za preučevanje stresa in produktivnosti</li>
                                    <li>Merjenje mestnega hrupa za koncerte, prireditve in urbanistično načrtovanje</li>
                                    <li>Raziskave izpostavljenosti zvoku v zaprtih prostorih</li>
                                    <li>Spremljanje hrupa, ki upošteva zasebnost, z razvrščanjem hrupa z umetno inteligenco v napravi</li>
                                </ul>
                            </div>
                            <div>
                                <span class="font-departure text-[#fff]">Opis:</span>
                                <div class="p-3">Brezžični senzorji merijo hrup v zaprtih prostorih/na prostem. Eden sledi decibelom, drugi pa dodaja klasifikacijo zvoka z umetno inteligenco v napravi z zasebnostjo. Uporabno za študije na delovnem mestu in spremljanje hrupa v mestih.</div>
                            </div>
                        </div>
                    </SensorCard>
                </div>
            </div>

            <div class="p-6 min-h-[30vh] w-[80%] m-auto">
                <span class="font-departure text-primary text-xl">Zakaj izbrati SPL?</span>
                <div class="mx-auto bg-white rounded-xl">
                    <h2 class="text-2xl font-bold mb-4">Senzorji ravni zvočnega tlaka (SPL)</h2>

                    <p class="text-slate-700 leading-relaxed mb-4">
                        Naši senzorji ravni zvočnega tlaka (SPL) so napredne, kalibrirane naprave, zasnovane za merjenje in analizo ravni hrupa v zaprtih prostorih in na prostem. Ti brezžični senzorji, ki so na voljo v dveh različicah, ustrezajo širokemu spektru aplikacij.
                    </p>

                    <p class="text-slate-700 leading-relaxed mb-4">
                        Prva različica meri samo raven decibelov in zagotavlja natančno spremljanje hrupa, kjer je zvočni tlak glavna skrb. Druga vključuje vsesmerni mikrofon, ki se aktivira nad 80 dB in zajema zvočne posnetke, obdelane na napravi. Z uporabo hitre Fourierjeve transformacije (FFT) se
                        posnetki pretvorijo v frekvenčni spekter za klasifikacijo virov hrupa, ki jo poganja umetna inteligenca. Zasebnost zagotavlja, da posnetki nikoli ne zapustijo naprave in se po klasifikaciji uničijo.
                    </p>

                    <p class="text-slate-700 leading-relaxed mb-4">
                        V zaprtih prostorih senzorji SPL pomagajo preučevati delovna okolja in njihov vpliv na stres in produktivnost. Na prostem spremljajo mestni hrup med dogodki, kot so koncerti, in tako pomagajo mestom ublažiti negativne učinke na prebivalce. Z ohišji, ki jih je mogoče
                        prilagoditi za notranjo in zunanjo uporabo, ti senzorji ponujajo vsestransko in zasebnostno rešitev za spremljanje in analizo hrupa.
                    </p>
                </div>
            </div>
        </div>

        <!-- Outdoor Sound -->
        <div class="w-full">
            <div class="py-5 grid gap-5 bg-[#1E201E] w-full">
                <span id="outdoor" class="text-white m-auto font-departure text-xl text-left w-[90%] pt-24">Zunanji senzor zvoka</span>
                <div class="m-auto w-[80%] flex items-center justify-center">
                    <SensorCard fileLeft="swarm-transparent.png" fileRight="swarm.png" class="rounded-xl ">
                        <div class=" h-full p-3 text-white flex flex-wrap lg:grid">
                            <div>
                                <span class="font-departure text-[#fff]">Najboljše za:</span>
                                <ul class="list-disc list-inside mt-1">
                                    <li>Klasifikacija zvoka, ki ohranja zasebnost</li>
                                    <li>Pametno spremljanje dogodkov</li>
                                    <li>Urbano načrtovanje in kartiranje hrupa</li>
                                    <li>Prepoznavanje virov hrupa (glasba, množice, promet itd.)</li>
                                    <li>Opozorila na podlagi pragov brez shranjevanja zvoka</li>
                                </ul>
                            </div>
                            <div>
                                <span class="font-departure text-[#fff]">Opis:</span>
                                <div class="p-3">
                                    Zvočni senzor z dvema mikrofonoma za kontekstualno spremljanje hrupa. Ko se raven hrupa spremeni, Edge AI v napravi takoj razvrsti vire, kot so stroji, glasba ali glasovi. Ves zvok se obdela lokalno in takoj izbriše, kar zagotavlja uporabne vpoglede brez
                                    shranjevanja podatkov.
                                </div>
                            </div>
                        </div>
                    </SensorCard>
                </div>
            </div>

            <div class="p-6 min-h-[30vh] w-[80%] m-auto">
                <span class="font-departure text-primary text-xl">Zakaj izbrati zunanji senzor ravni zvočne onesnaženosti (SPL)?</span>
                <div class="mx-auto bg-white rounded-xl">
                    Zunanji SPL zagotavlja natančne podatke o zvočnem tlaku v realnem svetu, ki odražajo dejanske akustične pogoje okolja. Z zajemanjem hrupa točno tam, kjer se pojavi, postane bistvena osnova za razumevanje vpliva na okolje, ocenjevanje skladnosti in izboljšanje dolgoročnega
                    načrtovanja. <br />
                    <br />
                    V kombinaciji z našim klasifikacijskim cevovodom Edge AI vam Outdoor SPL ne pove le, kako glasen je bil določen dogodek, temveč pomaga razkriti, kaj ga je povzročilo. <br />
                    <br />
                    Ne glede na to, ali gre za prometni tok, gradbene stroje ali aktivnost velike množice, pridobite kontekstualni vpogled, ki surove odčitke decibelov pretvori v uporabne informacije za mesta, prizorišča in operativne ekipe.
                </div>
            </div>
        </div>

        <!-- MHT -->
        <div class="w-full">
            <div class="py-5 grid gap-5 bg-[#35374B] w-full">
                <span id="mht" class="m-auto text-white font-departure text-xl text-left w-[90%] pt-24">Senzor vlažnosti lesa</span>
                <div class="m-auto w-[80%] flex items-center justify-center">
                    <SensorCard fileLeft="mht-transparent.png" fileRight="mht.png" class="rounded-xl ">
                        <div class=" h-full p-3 text-white flex flex-wrap">
                            <div>
                                <span class="font-departure">Najboljše za:</span>
                                <ul class="list-disc pl-6 space-y-1 pt-1">
                                    <li>Spremljanje ravni vlage v lesenih konstrukcijah</li>
                                    <li>Preprečevanje plesni, gnitja in strukturnih poškodb v lesenih stavbah</li>
                                    <li>Raziskave trajnostnih in inovativnih gradbenih materialov</li>
                                    <li>Zagotavljanje dolgoročne trajnosti in učinkovitosti lesenih konstrukcij</li>
                                </ul>
                            </div>

                            <div>
                                <span class="font-departure">Opis:</span>
                                <div class="p-3">
                                    Senzorji, nameščeni neposredno v lesu, za spremljanje ravni vlage, v kombinaciji s senzorji relativne vlažnosti/temperature v okolju. Pomagajo preprečevati plesen, gnitje in strukturne težave, kar podpira raziskave lesene gradnje in trajnostne gradnje.
                                </div>
                            </div>
                        </div>
                    </SensorCard>
                </div>
            </div>

            <div class="p-6 min-h-[30vh] w-[80%] m-auto">
                <span class="font-departure text-primary text-xl">Zakaj izbrati MC?</span>
                <div class="mx-auto bg-white rounded-xl">
                    <h2 class="text-2xl font-bold mb-4">Senzorji vlažnosti lesa (MC)</h2>

                    <p class="text-slate-700 leading-relaxed mb-4">
                        Naši senzorji vsebnosti vlage (MC) so specializirane naprave, zasnovane za zagotavljanje ključnih vpogledov v dinamiko vlage v lesenih konstrukcijah, kar zagotavlja dolgo življenjsko dobo in strukturno celovitost lesenih stavb. Ti senzorji podpirajo tako žično kot brezžično
                        komunikacijo, pri čemer je žična komunikacija prednostna zaradi omejenega dostopa po namestitvi.
                    </p>
                    <p class="text-slate-700 leading-relaxed mb-4">
                        Senzorji, nameščeni neposredno v les z vijaki v material, merijo vlago v samem lesu in ponujajo veliko več ustreznih podatkov kot standardni senzorji relativne vlažnosti (RH) in temperature (T). Za doseganje celovitega spremljanja običajno namestimo te senzorje v ovoj
                        (fasado) stavbe, dopolnjene s tremi dodatnimi senzorji RH/T, ki spremljajo stanje zraka v okolici.
                    </p>
                    <p class="text-slate-700 leading-relaxed mb-6">
                        Ta dvoslojni sistem pomaga analizirati interakcijo med vlago v lesu in vlažnostjo okolja ter zagotavlja bistvene podatke za preprečevanje plesni, gnitja in strukturne degradacije. Naši senzorji MC so idealni za lesene stavbe in raziskave trajnostnih materialov ter podpirajo
                        arhitekte, gradbenike in raziskovalce pri izboljšanju vzdržljivosti in učinkovitosti.
                    </p>
                </div>
            </div>
        </div>

        <!-- Grafana -->
        <div class="w-full">
            <div class="py-5 grid gap-5 bg-[#0F0E0E] w-full text-white">
                <span id="grafana" class=" font-departure text-xl text-left m-auto w-[90%] pt-24">Vizualizacija podatkov – Grafana nadzorna plošča</span>
                <div class="m-auto w-[80%] flex items-center justify-center">
                    <SensorCard fileLeft="grafana-test.png" fileRight="sketch.svg" class="shadow bg-white rounded-xl " rightClass="object-contain">
                        <div class=" h-full p-3 flex flex-wrap">
                            <div>
                                <span class="font-departure">Izvoz podatkov:</span>
                                <ul class="list-disc pl-8 pt-3 space-y-1">
                                    <li>CSV</li>
                                    <li>JSON</li>
                                </ul>
                            </div>

                            <div>
                                <span class="font-departure">Kratek opis:</span>
                                <div class="p-2">
                                    Vsi senzorji delujejo s programskim sistemom, ki združuje odprtokodne in prilagojene rešitve, pri čemer uporablja visokozmogljivo podatkovno bazo časovnih vrst za hitre poizvedbe na podlagi intervalov.
                                    <div class="border border-green-600/85 bg-green-600/10 w-min py-1 px-2 text-nowrap rounded-full text-sm text-green-600">Open Source</div>
                                </div>
                            </div>
                        </div>
                    </SensorCard>
                </div>
            </div>
            <div class="p-6 min-h-[30vh] w-[80%] m-auto">
                <span class="font-departure text-primary text-xl">Zakaj nadzorna plošča?</span>
                <div class="mx-auto p-6 bg-white rounded-xl">
                    <h2 class="text-2xl font-bold mb-4">Integracija programske opreme</h2>

                    <p class="text-slate-700 leading-relaxed mb-4">
                        Vsi senzorji so integrirani s priloženim programskim sistemom, ki je robustna kombinacija odprtokodnih rešitev in kode po meri. Visoko zmogljiva podatkovna zbirka časovnih vrst shranjuje meritve in podpira hitre intervalne poizvedbe.
                    </p>
                    <p class="text-slate-700 leading-relaxed mb-4">
                        Za vizualizacije Grafana izdela grafične nadzorne plošče stanja stavbe. Programska oprema podpira več uporabnikov, sheme dovoljenj, prilagojen sistem opozoril (e-pošta ali priljubljene storitve za neposredno sporočanje) in vizualizacije tlorisov po meri, ki temeljijo na
                        postavitvah, ki jih zagotovi arhitekt.
                    </p>
                    <p class="text-slate-700 leading-relaxed">Za napredno analizo je mogoče podatke izvoziti v poljubnem časovnem intervalu v standardnih formatih, kot sta CSV in JSON.</p>
                </div>
            </div>
        </div>

        <!-- Resources -->
        <div class="w-full">
            <div class="py-5 pb-32 grid gap-5 bg-[#007E6E] w-full text-white">
                <span id="resources" class=" font-departure text-xl text-left m-auto w-[90%] pt-24">Viri</span>
                <div class="m-auto w-[80%]">
                    <ul class="w-full space-y-5">
                        {#each { length: 1 } as _}
                            <a target="_blank" href="./user_manual.pdf" class="flex gap-4 items-start bg-white/5 p-2 rounded-xl group hover:bg-white/30">
                                <div class="grid gap-3 w-min font-departure border rounded-lg p-3 text-sm border-white/10 group-hover:bg-white/10 group-hover:shadow-lg">
                                    <img src="./pdf.svg" class="size-10" />
                                    <div>Uporabniški priročnik</div>
                                </div>
                                <div class="text-shadow-md">Datoteka vsebuje priročnike za vse naše senzorje, navodila za namestitev, podporo in pomoč s poverilnicami.</div>
                            </a>
                        {/each}
                    </ul>
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
        <div>Izdelal InnoRenew CoE</div>
    </a>
</footer>
