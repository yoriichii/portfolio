<template>
  <section class="p-5">
    <div class="text-center mt-5">
      <h1 class="text-4xl">My Work</h1>
      <div class="mt-1">
        <span class="text-lg">{ Click on a project to see more details }</span>
      </div>
    </div>
    <div class="main">
      <div
        class="card"
        v-for="(cardProject, index) in allCardProjects"
        :key="index"
      >
        <a :href="cardProject.url" target="_blank">
          <div class="card2">
            <img
              :src="cardProject.image"
              alt="Project Image"
              class="text-white h-[350px] rounded-md"
              width="460px"
            />
          </div>
        </a>
      </div>
    </div>
    <div v-if="loading" class="main">
      <div
        v-for="index in 6"
        :key="index"
        class="skeleton h-[350px] w-[350px] relative bottom-[3.5rem]"
      ></div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from "vue";
import commingProject from "@/assets/coming-project.webp";
import usernameGithubGif from "@/assets/username-github.gif";
import weatherApp from "@/assets/weather-app.gif";
import shopifyApi from "@/assets/shopify-api.gif";

const loading = ref(true);
const allCardProjects = ref([]);

onMounted(() => {
  setTimeout(() => {
    allCardProjects.value = [
      {
        image: usernameGithubGif,
        url: "https://username-github-search.vercel.app/",
      },
      { image: weatherApp, url: "https://weather-app-vuee.vercel.app/" },
      { image: shopifyApi, url: "https://shopify-api-integration.vercel.app/" },
      { image: commingProject, url: "" },
      { image: commingProject, url: "" },
      { image: commingProject, url: "" },
    ];
    loading.value = false;
  }, 1500);
});
</script>

<style scoped>
.main {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
  margin: auto;
  justify-items: center;
  max-width: 1200px;
  gap: 1.5rem;
  margin-top: 3.5rem;
  margin-bottom: 3.5rem;
}

.card {
  width: 100%;
  max-width: 460px;
  height: 350px;
  background-image: linear-gradient(163deg, #00ff75 0%, #3700ff 100%);
  border-radius: 10px;
  transition: all 0.3s;
  box-shadow: 0px 0px 10px 0px rgba(0, 255, 117, 0.3);
}

.card2 {
  width: 100%;
  max-width: 460px;
  height: 350px;
  border-radius: 10px;
  background-color: #1a1a1a;
  transition: all 0.2s;
}

.card2:hover {
  transform: scale(0.98);
  border-radius: 10px;
  cursor: pointer;
}

.card:hover {
  box-shadow: 0px 0px 30px 1px rgba(0, 255, 117, 0.3);
  border-radius: 10px;
}
</style>
