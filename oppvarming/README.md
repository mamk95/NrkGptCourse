# Oppvarming

Dette er en oppvarminsøvelse for å sjekke at alt fungerer på din PC, og for å gjøre deg komfortabel med Vue.

Husk at dette arrangementet hadde noen forhåndskrav i innkallingen. Hvis du ikke allerede har gjort det, må du laste ned og installere VS Code og Node.js.
- VS Code: https://code.visualstudio.com/
- Node: https://nodejs.org/ (versjon 18 eller nyere)

Gjør følgende:
1. Last ned denne mappen fra GitHub. Klikk på den store grønne "Code"-knappen her på GitHub, så på "Download ZIP"
1. Åpne "oppvarming"-mappen i VS Code
1. I VS Code, klikk på "Extensions"-knappen i den vertikalen menyen til venstre. Søk etter "volar" og installer utvidelsen (Den heter muligens "_Vue Language Features (Volar)_")
1. I VS Code, i menyen helt øverst på skjermen, trykk på "Terminal" og så på "New Terminal"
1. I terminalen på bunnen av skjermen, skriv "npm install" (ignorer feilmeldinger som "WARN depricated" og eventuelle vulnerabilities)
1. I terminalen på bunnen av skjermen, skriv "npm run dev"
1. Kommandoen over gir deg en nettside (f.eks. http://localhost:5173). Naviger til denne nettsiden
1. Test nettsiden og se at alt fungerer. Du skal ha en knapp som sier "Øk", og hver gang du klikker på den skal tallet ved siden av økes med 1
1. Se deg rundt i koden. Det viktigste ligger i mappen "src/components", hvor du finner filen "Telling.vue"

Valgfrie ekstraoppgaver:
- Legg til CSS som gjør knappen rød. Se presentasjonen på GitHub for å finne koden jeg tidligere viste frem
- Hva skjer om du bytter ut `const tall = ref(0)` med `var tall = 0`, og endrer `tall.value++` til `tall++`?