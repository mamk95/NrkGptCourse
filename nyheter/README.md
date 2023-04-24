# nyheter

Det er godt mulig dere sitter igjen med haugevis av spørsmål. Det er vanskelig å gå gjennom absolutt alt som trengs for alle kunnskapsnivåer. Hvis du sitter fast, prøv dette:
- Spør ChatGPT!
- Spør meg. Jeg er ikke farlig 😊
- Søk på nettet. Her er nøkkelordene dere trenger:
   - Hvis dere lurer på noe av det som går inn i `<template>`, søk etter "HTML [ditt spørsmål]". Hvis det er noe Vue-relatert, søk etter "Vue 3 template [ditt spørsmål]"
   - Hvis dere lurer på noe av det som går inn i `<script setup>`, søk etter "Vue 3 composition [ditt spørsmål]", eller les https://vuejs.org/guide/introduction.html (Merk: skru på "Composition" oppe i venstre hjørne, ikke "Options").
   - Hvis dere lurer på noe av det som går inn i `<style>`, søk etter "CSS [ditt spørsmål]"
   - Hvis dere lurer på noe relatert til RSS-biblioteket, altså det som henter nyheter fra NRK, les dokumentasjonen her: https://www.npmjs.com/package/rss-to-json
   - Hvis dere lurer på noe relatert til kommunikasjon med OpenAI-APIet, les dokumentasjon her: https://www.npmjs.com/package/openai

Husk at dette arrangementet hadde noen forhåndskrav i innkallingen. Hvis du ikke allerede har gjort det, må du laste ned og installere VS Code og Node.js.
- VS Code: https://code.visualstudio.com/
- Node: https://nodejs.org/ (versjon 18 eller nyere)

**Merk**: Hvis du i stegene under bruker min OpenAI-nøkkel, må du **IKKE** laste den opp til GitHub. Da vil nøkkelen bli automatisk deaktivert av OpenAI, og ingen av dere vil klare å fortsette kurset.

Gjør følgende:
1. Last ned denne mappen fra GitHub. Klikk på den store grønne "Code"-knappen her på GitHub, så på "Download ZIP"
1. I "nyheter"-mappen vil du finne flere undermapper. Velg din vanskelighetsgrad, og bruk instruksjonene under pluss instruksjonene i undermappen for å utføre oppgaven
    - **Husker/kan ingenting om frontend (HTML, JavaScript, CSS)**: Bruk fasiten, og prøv å endre på kode for å gjøre det til ditt egen design og prosjekt. Endre litt på ChatGPT-prompten for å se hva som passer deg best. Kanskje du ønsker at nyhetene skal rime? Eller at det aldri skal brukes et ord som begynner på bokstaven "e"?
    - **Kan litt HTML, JavaScript og CSS**: Bruk mappen "enkel"
    - **Kan litt React/Vue/Angular/Svelte eller lignende**: Bruk mappen "medium"
    - **Jeg er ekspert på frontendutvikling**: 
1. Åpne din ønskede mappe fra steget over i VS Code
1. I VS Code, klikk på "Extensions"-knappen i den vertikalen menyen til venstre. Søk etter "volar" og installer utvidelsen (Den heter muligens "_Vue Language Features (Volar)_"). Denne installerte du muligens i oppvarmingsoppgaven, da kan du hoppe over dette steget.
1. Du trenger en OpenAI api-nøkkel og organization-nøkkel. Jeg anbefaler at du bruker din egen, fordi du da kan fortsette å bruke denne applikasjonen etter du drar hjem. Hvis du ikke ønsker å bruke din egen, kan du bruke min - denne deler jeg gjerne med deg, men jeg skrur av tilgangen etter kurset.
    - Du får 5 dollar gratis i 3 måneder av OpenAI på den første kontoen du knytter til ditt telefonnummer. Dette er samme konto som du bruker til ChatGPT om du har en konto der. Jeg tipper at dette kurset vil bruke rundt 0.01 dollar, altså har du mer enn nok gratis credits fra OpenAI. $5 er omtrent 750 API-kall. Slik får du tilgang til dette:
    1. Gå til https://platform.openai.com/account, og logg inn med din ChatGPT-konto. Hvis du har flere kontoer, må du bruke den første du opprettet for å få $5.
    1. Etter innlogging, vil du se at du har alt fra $5 til $18 dollar på denne nettsiden: https://platform.openai.com/account/usage. Hvis ikke, og hvis du har flere kontoer, prøv dine andre kontoer. Hvis det fortsatt ikke går, spør meg om å få låne min :)
    1. Gå til https://platform.openai.com/account/org-settings. Her finner du din "Organization ID". Ta vare på denne, du trenger den i koden din.
    1. Gå til https://platform.openai.com/account/api-keys, og opprett en ny API-nøkkel. Ta vare på denne, du trenger den i koden din. Den hemmelige nøkkelen vil bare vises 1 gang, så husk å noter den ned etter du har laget den.
1. Følg resten av instruksjonene fra mappen du valgte over.
