<template>
    <div class="News">
        <div v-for="story in stories" :key="story.url" class="story">
            <h2>{{ story.title }}</h2>

            <!-- Oppgave: Legg til feltene/bildene du ønsker å vise her. -->
        </div>
    </div>
</template>

<script setup>
import { parse } from "rss-to-json";
import { Configuration, OpenAIApi } from "openai";

const OpenAiConfiguration = new Configuration({
  organization: "<din org-key, se info i oppgaveteksten>", // https://platform.openai.com/account/org-settings
  apiKey: "<din api-key, se info i oppgaveteksten>", // https://platform.openai.com/account/api-keys
});

const stories = (await FetchNews());

async function FetchNews() {
  const stories = [
    {
      title: "Denne arrayen må endres på",
    },
    {
      title: "Arrayen må fylles opp av nyhetssaker fra NRK"
    }
  ];

  try {
    console.log("Henter nyheter fra NRK sin RSS");
    const rss = await parse("https://www.nrk.no/toppsaker.rss");
    console.log("Ferdig å hente nyheter fra NRK sin RSS");
    
    /* Oppgave: Gå gjennom dataen som ligger i rss-objektet over, og legg det til i stories-arrayen. Bruk dokumentasjonen til RSS-biblioteket: https://www.npmjs.com/package/rss-to-json */

    console.log("Ferdig å hente og oppsummere nyheter");
  } catch (error) {
    alert("Error fetching RSS feed");
    console.error(error);
  }

  return stories;
}

async function AiSummarize(newsStoryUrl) {
  // Hvis du vil teste nettsiden uten å bruke opp penger på OpenAI, fjern // fra de to linjene under. Da vil den returnere "Test123" for hver nyhet etter 2 sekunder (2000 millisekunder)
  // await new Promise((resolve) => setTimeout(resolve, 2000));
  // return "Test123";

  const openai = new OpenAIApi(OpenAiConfiguration);

  try {
    const result = await openai.createChatCompletion({
      /* Oppgave: Bruk biblioteket sin dokumentasjon for å finne ut hva som skal skrives her. Dokumentasjon: https://www.npmjs.com/package/openai */
    });

    /* Oppgave: returner teksten fra result-objektet over. Bruk dokumentasjonen: https://www.npmjs.com/package/openai */
    return "Test123";
  } catch (error) {
    alert("Error summarizing news story");
    console.error(error);
    throw error;
  }
}
</script>
  
<style scoped lang="css">
.News {
    display: flex;
    flex-direction: column;
    gap: 8px;
    margin: 0 auto;
    max-width: 600px;
}

.story {
    /* Oppgave: Legg til din stil her */
}

.story-img {
    width: 100%; /* Stops img from overflowing parent */
}
</style>
  