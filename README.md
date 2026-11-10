# eSolar – naujo dizaino demo (WordPress + WooCommerce + XStore)

Gyvas demo: https://arvydastry.github.io/esolar/ (GitHub Pages; puslapiai pažymėti `noindex`, kad demo nepatektų į paiešką – prieš tikrą paleidimą žymą išimti).

Atidaryti: `index.html` (arba `python3 -m http.server 8765` → http://localhost:8765).

- `index.html` – **v5 „Parallax“ (aktualus demo)**: nauja kryptis – paralaksas, Salient tipo elementai, XStore pagrindinės funkcijos.
- `v4-light.html` – ankstesnė šviesi kryptis (v2 + duomenų komponentai) – atmesta.
- `v2-light.html`, `v3-unique.html`, `v1-dark.html` – ankstesni variantai, palikti palyginimui.

## v5 dizaino kryptis
- Identitetas: šiltas popierius `#F3F1EC` / rašalas `#0D1014` / saulės geltona `#FFC531`; šriftai **Bricolage Grotesque** (antraštės) + **Instrument Sans** (tekstas). Logotipo ženklas perpieštas SVG (lankas, segmentuota saulė, spinduliai) – veikia ant tamsaus ir šviesaus fono.
- **Hero (atnaujinta 2026-11-10, B2C):** trys namų scenos viename „ekrane“ su suapvalintu rėmu – saulės elektrinė ant namo stogo (dronas), elektromobilio įkrovimas prie namo, šeima prie namų. Antraštė keičiasi kartu su scena („Jūsų stogas – jūsų elektrinė“ / „Jūsų kiemas – jūsų degalinė“ / „Jūsų namai – jūsų energija“), perėjimas – besiplečiantis „saulės“ apskritimas iš grojaraščio miniatiūros. Dešinėje grojaraštis su miniatiūromis, progreso linija ir faktu (1 scenoje – gyvas saulės laikas Panevėžiui). Virš antraštės – APVA paramos juostelė. Slenkant rėmas sumažėja ir pritemsta, turinys užslenka ant jo. Mobile – grojaraštis virsta trimis skirtukais apačioje.
- Paralaksas: hero video su „sticky“ efektu (turinys užslenka ant video), `data-speed` sluoksniai „Apie“ sekcijoje (dvi nuotraukos + skaičiaus kortelė juda skirtingu greičiu), fono paralaksas skaičių juostoje, paramos foto ir kontaktų video, projektų nuotraukos juda rėmuose, milžiniškas „esolar“ žodis footer'yje.
- Salient tipo elementai: split-text antraštės (žodžiai išnyra), bėganti juosta (marquee) reaguojanti į slinkimo greitį, **fancy boxes** su 3D pakreipimu ir hover aprašymu, **milestone** skaitikliai ant video fono, **pinned horizontalus** „Kaip dirbame“ (5 žingsnių kortelės su nuotraukomis ir horizontaliu paralaksu + CTA kortelė, mobile – swipe), **image hotspots** su tikra kliento nuotrauka, mask-reveal projektų tinklelis su pasirinktiniu kursoriumi „Žiūrėti“, atsiliepimų slideris, besisukantis APVA ženkliukas, mega meniu, fullscreen mobilus meniu.
- Unikalūs duomenų komponentai (išliko): gyvas saulės laikas Panevėžiui hero kortelėje, skaičiuoklė su galios pakopų kaina ir 12 mėn. gamybos grafiku.
- Visos animacijos gerbia `prefers-reduced-motion`; video įkeliami tik pasirodžius ekrane.

## Demo / vietos ženklai (pakeisti prieš gamybą)
- Prekės, kainos, ženklai „Sandėlyje“, „−7 %“; gamintojų pavadinimai „Montuojame“ juostoje (įdėti tikrus logotipus).
- Projektų užrašai (objektas, vieta, metai, galia) ir atsiliepimai – demo tekstai, pakeisti tikrais.
- Skaičiai: 700+ objektų, 10+ metų, 24 val., 28 d.; „sava brigada“, garantijos – suderinti su klientu.
- Hotspot'ų aprašymai (440 W, 10 kW + 10 kWh, 11 kW) – pritaikyti pagal realų objektą.
- Hero scenų faktai („11 kW ≈ 60 km per valandą“, „10 kWh kaupiklis padengia vakaro ir nakties suvartojimą“) – orientaciniai, suderinti su klientu. Hero video – Pexels; idealu pakeisti tikrais kliento objektų kadrais.
- Skaičiuoklės koeficientai: 1 kW ≈ 1 000 kWh, 750–980 €/kW pagal galią, +12 % antžeminėms, APVA 255 €/kW iki 10 kW, 0,25 €/kWh; mėnesinis pasiskirstymas – orientacinis.
- „Kaip dirbame“ kortelių nuotraukos – Pexels; idealu pakeisti tikromis eSolar komandos ir objektų nuotraukomis.
- Forma – demo (nesiunčia); naujienlaiškis – demo.

## Šaltiniai
- Tekstai, nuotraukos (dronų foto `assets/esolar/web/`), rekvizitai: esolar.lt.
- Pexels video: hero scenos 7211094 (moduliai ant namo stogo stambiu planu – parinko klientas; 6 s klipas, todėl leidžiamas 0,8× greičiu ir pabaigoje sulaikomas paskutinis kadras), 4818143 (elektromobilio įkrovimas prie namo), 5429459 (šeima prie namų); 20653303 (skaičių juostos fonas – parinko klientas), 14067718 (skaičiuoklės fonas), 15046856 (kontaktai). Foto: 12243093, 9875418, 39057093; „Kaip dirbame“ kortelės – 7415049, 5831658, 9870133, 9875411, 38171111. Gamybai video laikyti savo serveryje (1280×720, 2–4 MB), ne Pexels CDN.

## Perkėlimas į WordPress + WooCommerce + XStore
| Demo elementas | XStore / WP įgyvendinimas |
|---|---|
| Skaidrus header → fiksuotas, mega meniu, mobilus fullscreen meniu | XStore Header Builder (transparent + sticky variantas), XStore Mega Menu, Mobile panel |
| Hero: 3 video scenos, besikeičianti antraštė, grojaraštis | Slider Revolution (bundled su XStore): 3 video skaidrės su sluoksniais ir navigacijos skirtukais; arba HTML widget su demo JS (scenų logika ~40 eil.). Sticky ir „rėmo“ efektas – CSS child-theme |
| Bėganti juosta | XStore Elementor „Marquee“ / Running text widget; greitis pagal slinkimą – demo JS |
| Paralakso sluoksniai (`data-speed`), fono paralaksas | Elementor Pro Motion Effects (scrolling/mouse) arba demo GSAP skriptas (vienas child-theme failas, `data-speed` atributai per Elementor Advanced → Attributes) |
| Fancy boxes | XStore „Banner“ widget su hover efektais + CSS; 3D tilt – demo JS |
| Skaitikliai ant video fono | Elementor sekcija su video fonu + Counter widget'ai |
| Pinned horizontalus procesas su nuotraukų kortelėmis | Elementor sekcija + demo GSAP ScrollTrigger (pin); kortelės – XStore „Banner“/Image Box; mobile – XStore Slider/Carousel |
| Image hotspots | XStore Hotspots / „Shop the look“ (su Woo prekių nuorodomis) arba Elementor Pro Hotspot |
| Prekės, kategorijų filtrai, krepšelis | XStore Woo „Products“ carousel + „Product Categories“ widget'ai, tikri Woo produktai, XStore Sales Booster ženklai |
| Projektai | XStore Portfolio (Custom Post Type) arba Elementor Gallery; mask reveal – demo JS |
| Atsiliepimai | XStore Testimonials widget |
| Skaičiuoklė, saulės laikas | HTML widget + demo JS (be papildomų įskiepių) |
| APVA ženkliukas, kontaktų forma | HTML/SVG widget; Contact Form 7 arba Fluent Forms |
| Šriftai | XStore Typography → Google Fonts „Bricolage Grotesque“ + „Instrument Sans“ (arba self-host) |
| Animacijos | GSAP 3.12 + ScrollTrigger kaip vienas child-theme skriptas (~250 eil.), `prefers-reduced-motion` gerbiamas |
