# nyheter

Husk å lese instruksjonene i mappen "nyheter" også. Du skal følge både disse instruksjonene og de i "nyheter"-mappen.

Etter du har følgt instruksjonene i "nyheter"-mappen, gjør følgende:
1. I mappen "src/components" finner du filen "News.vue". Rundt linje 17 til 20 i denne filen må du skrive inn din OpenAI API-nøkkel og organisasjons-ID. Instruksjoner på hvor du finner disse to nøklene ligger i instruksjonene i "nyheter"-mappen
1. I VS Code, i menyen helt øverst på skjermen, trykk på "Terminal" og så på "New Terminal"
1. I terminalen på bunnen av skjermen, skriv "npm install" (ignorer feilmeldinger som "WARN depricated" og eventuelle vulnerabilities)
1. I terminalen på bunnen av skjermen, skriv "npm run dev"
1. Kommandoen over gir deg en nettside (f.eks. http://localhost:5173). Naviger til denne nettsiden
1. Du har nå en fungerende nettside, men du får ikke ut oppsummeringen. I "News.vue" ser du to oppgaver (trykk CTRL+F for å søke, og søk etter "oppgave").
1. Den første oppgaven er å sende URLen til NRK-nyheten til OpenAI. Du finner oppgaveteksten i koden. Hvis du sitter helt fast, kan du ta en titt på fasiten i egen mappe.
1. Den andre oppgaven går ut på å fikse designet per nyhetssak. Her er det bare å være oppfinnsom, men to tips er følgende CSS:
    - `background: red;` vil gjøre bakgrunnen rød
    - `border: 1px solid black;` vil gi nyheten en firkantet ramme. Hvis du ønsker å ha en avrundet ramme, bruk i tillegg `border-radius: 12px;`
1. Test nettsiden og se at alt fungerer. Merk at det tar litt tid å oppsummere hver nyhet, så du må kanskje vente litt. Du kan trykke på F12-knappen for å få opp utviklerkonsollen, så trykke på "Console". Der vil du få oppdateringer på fremgangen til oppsummeringen.
1. Se deg rundt i koden. Det viktigste ligger i mappen "src/components", hvor du finner filen "News.vue"

**Merk**: I mappen "src/components" finner du filen "News.vue", rundt linje 32, finner du kode som begrenser antall nyheter som sendes til OpenAI. Hver nyhet tar rundt 5 sekunder å oppsummere, så hvis du ønsker 3 nyheter vil nettsiden bruke rundt 15 sekunder. `slice(0, 1)` gir deg første nyhet, `slice(0, 2)` gir deg de to første, `slice(0, 3)` gir deg de tre første, osv. Du står fritt til å endre på denne, men mens du tester nytt design og nye prompts anbefaler jeg at du holder den lav, slik at du raskt får testet koden din uten å måtte vente så lenge.

**Merk**: Hvis du planlegger å laste opp koden din (f.eks. til GitHub), husk å fjerne OpenAI-nøkkelen din fra "News.vue". Glemmer du dette vil noen enten stjele den og bruke opp pengene dine, eller så vil OpenAI oppdage det og stenge nøkkelen. Hvis nøkkelen din stenges, må du bruke instruksjonene over for å opprette en ny nøkkel.


Valgfrie ekstraoppgaver:
- I mappen "src/components" finner du filen "News.vue". Rundt linje 68 finner du prompt'en som sendes til OpenAI. Prøv å endre på denne til ditt eget ønske. Få nyhetene til å rime, sørg for at hver nyhet har en positiv spinn, eller få den til å oppdikte nyheter.
- I mappen "src/components" finner du filen "News.vue". Rundt linje 68 finner du prompt'en som sendes til OpenAI. Endre denne slik at det også genereres en overskrift. Test objektive overskrifter, test clickbait overskrifter, og både korte og lange overskrifter.
- Vanskelig: Gjør koden din sikker å laste opp til GitHub direkte uten endring. Se f.eks. https://jasonwatmore.com/post/2022/05/28/vue-3-vite-access-environment-variables-from-dotenv-env. Husk at du må legge til `env`-filen i `.gitignore`.
- Vanskelig: Klarer du å vise frem en og en nyhet på nettsiden etterhvert som de blir oppsummert av GPT? Akkurat nå må nettsiden vente på at alle nyhetene blir oppsummert før den viser frem noe. Hint: opprett en ny komponent/fil som tar seg av oppsummeringen. Send inn URLen til denne komponenten. Bruk så `<Suspense>` på samme måte som i "src/App.vue".