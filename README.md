# Socialinių paslaugų valdymo prototipas

Veikiantis socialinių paslaugų valdymo demonstracinis prototipas. Visos pasiūlyme išvardytos naudotojų funkcijos turi ekranus ir veikiančius demonstracinius scenarijus.

## Kaip paskelbti per GitHub Pages

1. Išarchyvuokite ZIP failą kompiuteryje.
2. Sukurkite GitHub repozitoriją norimu neutraliu pavadinimu, pavyzdžiui, `socialiniu-paslaugu-valdymas`.
3. Į repozitorijos pagrindinį katalogą įkelkite VISUS išarchyvuotus failus. `index.html`, `app.js`, `style.css`, piktogramos, `sw.js` ir `manifest.webmanifest` turi būti viename kataloge. Nekelkite paties ZIP ir nekelkite vien tik `index.html`.
4. Atidarykite repozitorijos **Settings → Pages**. Pasirinkite **Deploy from a branch**, šaką **main** ir katalogą **/(root)**, tuomet išsaugokite.
5. Kai paskelbimas bus baigtas, atidarykite GitHub Pages pateiktą nuorodą. Tokia nuoroda tinka ir atidaryti telefone.

Paketui nereikia `npm install`, kompiliavimo ar papildomo serverio. Visi keliami failai yra šio ZIP pagrindiniame kataloge; nuorodos pritaikytos GitHub Pages repozitorijos keliui.

## Išbandymas

Atidarykite paskelbtą svetainę. Viršuje galima perjungti administratoriaus / koordinatoriaus ir bet kurio iš 63 darbuotojų peržiūrą.

1. Administratoriaus aplinkoje atidarykite klientą, redaguokite kontaktus, artimųjų pranešimų nustatymus ir teikiamas paslaugas.
2. Grafike sukurkite vizitą. Persidengimai, neatvykimai ir viršytas mėnesio krūvis blokuojami.
3. Darbuotojų skiltyje pažymėkite neatvykimą ir perkelkite pasirinktus vizitus pavaduojančiam darbuotojui.
4. Pasirinkite darbuotojo peržiūrą, pradėkite vizitą, suteikite naršyklės GPS leidimą, pasirinkite užrašus, įveskite komentarą ir užbaikite laiką.
5. Darbuotojas ir klientas pasirašo ekrane; patvirtinus išsaugomas vizitas, abu parašai, faktinė trukmė ir GPS rezultatai.
6. Administratoriaus skiltyje „Pranešimai“ atsiranda suformuotas demonstracinis laiškas kiekvienam įjungtam artimojo kontaktui. Jame išsaugomas vizito pabaigos turinio momentinis vaizdas.
7. Tabeliuose pasirinkite laikotarpį, darbuotoją, klientą ar paslaugą; peržiūrėkite dienomis, paslaugų ar vizitų suvestinę ir eksportuokite CSV.

## Pasiūlymo funkcijų atitikimas

| Pasiūlymo funkcija | Prototipas |
| --- | --- |
| Klientų kortelės ir kontaktai | Klientų sąrašas, kūrimas, redagavimas, būsenos ir paieška |
| Artimųjų kontaktai | Keli gavėjai su individualiais pranešimų pasirinkimais |
| Paslaugos ir istorija | Paslaugų tipų administravimas, paslaugų priskyrimas klientui, vizitų istorija |
| Darbuotojai | 63 demonstraciniai darbuotojai, kortelės, kontaktai ir krūvio redagavimas |
| Grafikai ir užimtumas | Savaitinis kalendorius bei sąrašas, filtrai, vizitų planavimas ir redagavimas |
| Pavadavimai | Atostogos, liga ar kitas neatvykimas; pasirinkto vizitų rinkinio perkėlimas |
| Krūvio kontrolė | Darbuotojo ir kliento persidengimų, neatvykimų ir mėnesio limito patikra |
| Mobilus PWA vaizdas | Darbuotojo dienos grafikas, manifestas, piktogramos ir service worker |
| Start / stop, GPS | Tikras naršyklės laikas, geolocation API, tikslumas ir aiškus nesuteikto leidimo registravimas |
| Užrašai | Keli administruojami pasirinkimai ir laisvas komentaras, juodraščio išsaugojimas |
| Pasirašymas ekrane | Du privalomi pointer įvestį palaikantys canvas, išsaugojami PNG |
| Artimųjų informavimas | Automatinis turinio suformavimas ir gavėjų istorija demonstraciniu režimu |
| Tabeliai | Planuotos ir faktinės valandos, darbuotojo išklotinė dienomis, neatvykimai |
| Suvestinės ir eksportas | Darbuotojų, vizitų, paslaugų suvestinės ir CSV su lietuviškų simbolių palaikymu |
| Rolės | Atskira administratoriaus ir darbuotojo demonstracinė navigacija; veiksmų patikra |

## Mėnesio tabelis

Skiltyje „Tabeliai ir suvestinės“ pagrindinis vaizdas yra „Mėnesio tabelis“: darbuotojai pateikiami eilutėse, mėnesio dienos stulpeliuose. Mėnesį galima keisti rodyklėmis arba mėnesio pasirinkimu.

- Viršutinis langelio skaičius – faktinės užbaigtų vizitų valandos. „p“ apačioje – visų tos dienos vizitų planas.
- AT – atostogos, L – liga, N – kitas neatvykimas. Savaitgaliai ir šiandiena išskirti fono spalva.
- „·“ – vizitų nėra; „–“ – yra planas, bet dar nėra užbaigtų vizitų; „●“ – vizitas vyksta.
- Paspaudus dieną, atidaromi tik to darbuotojo tos dienos vizitai. Paspaudus darbuotojo vardą, atidaroma visų laikotarpio dienų išklotinė.
- Darbuotojų vardai, mėnesio sumos ir lentelės antraštės išlieka matomi slenkant. Apačioje pateikiamos dienų ir mėnesio bendros sumos.
- Pagal nutylėjimą rodomi darbuotojai su vizitais ar neatvykimais. „Rodyti ir be įrašų“ leidžia įtraukti visą sąrašą.
- Ankstesnė bendra lentelė išsaugota skiltyje „Darbuotojų suvestinė“.
- Nuokrypis = užbaigtų vizitų faktinės valandos minus TŲ PAČIŲ užbaigtų vizitų planinės valandos. Būsimi ir neužbaigti vizitai neįtraukiami į šį palyginimą. Tai nėra mėnesio darbo laiko normos trūkumo apskaičiavimas.
- Mėnesio CSV turi atskiras darbuotojo fakto, plano ir neatvykimų eilutes bei stulpelius visoms mėnesio dienoms. Suvestinės eksportas atitinka pasirinktus filtrus.

## Demonstravimo ribos

- Duomenys išsaugomi tik šios naršyklės localStorage. Nėra bendros kelių naudotojų serverio duomenų bazės.
- Peržiūros perjungimas imituoja roles. Tai nėra produkcinė autentifikacija ar saugi prieigos kontrolė. Auth0, .NET, SQL Server ir Azure paslaugos šiame prototipe nekonfigūruotos.
- Tikri el. laiškai nesiunčiami. Laiško gavėjas, tekstas ir laikas įrašomi į demonstracinę istoriją.
- GPS fiksuojamas tik gavus naršyklės leidimą HTTPS / localhost aplinkoje. Nesuteikus leidimo, rezultatas aiškiai pažymimas; koordinačių sistema neišgalvoja. Iš anksto užpildyti istoriniai GPS ir parašai pažymėti kaip demonstraciniai.
- PWA diegimas priklauso nuo naršyklės palaikymo. Pradinio programos apvalkalo talpinimas nėra papildomas pasiūlyme nenumatytas darbo be ryšio ir sinchronizavimo modulis.
- Išbrauktų pasiūlymo funkcijų (buhalterijos integracijos, Dokobit, artimųjų portalo, atskiros iOS / Android programos) nėra.

## Failai

- `index.html` – pradinis puslapis.
- `app.js` – visos demonstracinės sąveikos ir duomenys.
- `style.css` – kompiuteriui ir telefonui pritaikytas stilius.
- `manifest.webmanifest`, `sw.js`, `icon.svg`, `icon-192.png`, `icon-512.png` – PWA aprašas ir piktogramos.
- `.nojekyll` – statinių failų pateikimas GitHub Pages.

Kliento įmonės pavadinimo, pradinio pasiūlymo dokumento, prieigų raktų ir ankstesnio talpinimo konfigūracijos pakete nėra. Visi darbuotojų, paslaugų gavėjų ir artimųjų duomenys yra demonstraciniai.
