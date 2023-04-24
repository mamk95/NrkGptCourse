<template>
    <div class="News">
        <div v-for="story in stories" :key="story.url" class="story">
            <h2>{{ story.title }}</h2>

            <img v-if="story.imgUrl" :src="story.imgUrl" class="story-img" />

            {{ story.aiDescription }}
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
  const stories = [];

  try {
    console.log("Henter nyheter fra NRK sin RSS");
    const rss = await parse("https://www.nrk.no/toppsaker.rss");
    console.log("Ferdig å hente nyheter fra NRK sin RSS");
    
    const limitedStories = rss.items.slice(0, 1); // Slice(0, 3) gives us the three first news stories. If we were to send all 100 stories to GPT, the page would be loading for too long.

    for (const story of limitedStories) {
      console.log("Jobber med denne nyheten: " + story.title);
      stories.push({
        title: story.title,
        url: story.link,
        originalDescription: story.description,
        aiDescription: await AiSummarize(story.link),
        date: new Date(story.date),
        imgUrl: story.media?.thumbnail?.url,
      });
    }

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
      model: "gpt-3.5-turbo",
      messages: [
        {
          role: "user",
          content: "Kan du oppsummere denne nyheten? " + newsStoryUrl,
        },
      ],
    });

    return result.data.choices[0].message?.content;
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
    padding: 8px;
    border: 1px solid black;
    border-radius: 12px;
}

.story-img {
    width: 100%; /* Stops img from overflowing parent */
}
</style>
  