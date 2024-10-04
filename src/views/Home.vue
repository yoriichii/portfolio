<template>
  <div class="flex flex-col items-center px-4 py-24">
    <img class="w-36 h-36 rounded-full" src="../assets/my-pf.png" />
    <h1 class="mt-5">Sovan Dara, Creator</h1>
    <span class="w-12 h-1 bg-purple-600 rounded mt-2 mb-4"></span>
    <h2>begins with a passion.</h2>
    <!------------------ paragraph section -------------->
    <div>
      <div class="ml-5 mt-16">
        <h1 class="mb-8">1-minute read!</h1>
        <blockquote>
          <p class="border-l-2 pl-5 max-w-[50rem]">
            wasn't perfect. I always have curiosity about how things work around
            me. I learned about web developer by keep doing things over and
            over, I gained knowledge and perfection along the way. I wasn't even
            aware of that. Blogging isn't just about writing code snippets or
            tutorials; it's about connecting with others, sharing knowledge, and
            growing as a developer. That's why I do it I love the journey, and I
            want to bring others along with me.
          </p>
        </blockquote>
      </div>
    </div>
        <!------------------ Social section -------------->
    <div class="mt-24 text-2xl">MY SOCIAL NETWORKS!</div>
    <div class="flex flex-row gap-7 mt-24 cursor-pointer">
      <div v-for="(iconImage, index) in iconSoial" :key="index">
        <a :href="iconImage.url" target="_blank">
          <img
            :src="iconImage.icon"
            :alt="iconImage.alt"
            :style="styleIcon"
            class="hover:scale-110 transition duration-100 ease-in-out"
          />
        </a>
      </div>
    </div>
        <!------------------ About section -------------->
    <div class="px-4 py-24 max-w-[50rem]">
      <div class="mb-5 text-2xl"><strong>A bit more about me</strong></div>
      <p>
        My full name is <strong class="italic">Puth Sovandara</strong> currenly
        I'm a junior developer at solution company.
      </p>
      <div class="mt-12 mb-10 text-3xl underline"><strong>Edcuation</strong></div>
      <timeLineVue :events="timelineEventsEdcuation" />
      <div class="mt-8 mb-10 text-3xl underline"><strong>Work Experience</strong></div>
      <timeLineVue :events="timelineEventsWork" />
    </div>
    <!------------------ Skill section -------------->
  </div>
  <section>
      <div class="relative bottom-36">
        <skillSlider :skills="skills"/>
      </div>
    </section>
</template>

<script setup>
import { ref } from "vue";
import timeLineVue from "../components/time-line.vue";
import skillSlider from "../components/skill-slider.vue";
import tailwindLogo from "../assets/tailwind.webp"
const iconSoial = ref([
  {
    name: "facebook",
    icon: "https://www.freepnglogos.com/uploads/facebook-logo-icon/facebook-logo-icon-file-facebook-icon-svg-wikimedia-commons-4.png",
    url: "https://web.facebook.com/YanKashimo/",
    alt: "facebook",
  },
  {
    name: "linkin",
    icon: "https://imgs.search.brave.com/GpB5WQlesvec2MXDXDV3SmKb0pzSJzyH667WAzbxGcs/rs:fit:500:0:0:0/g:ce/aHR0cHM6Ly91cGxv/YWQud2lraW1lZGlh/Lm9yZy93aWtpcGVk/aWEvY29tbW9ucy9j/L2NhL0xpbmtlZElu/X2xvZ29faW5pdGlh/bHMucG5n",
    url: "https://www.linkedin.com/in/sovandara-puth-412224204?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=ios_app",
    alt: "linkin",
  },

  {
    name: "youtube",
    icon: "https://imgs.search.brave.com/xz_IZKS25qu0im1_T8aId19dYKKC8J9Fw8ImvIayhEw/rs:fit:500:0:0:0/g:ce/aHR0cHM6Ly9mcmVl/bG9nb3BuZy5jb20v/aW1hZ2VzL2FsbF9p/bWcvMTY1NjUwNDI4/OXlvdXR1YmUtbG9n/by1wbmctd2hpdGUt/Y2lyY2xlLnBuZw",
    url: "#",
    alt: "youtube",
  },
  {
    name: "telegram",
    icon: "https://www.freepnglogos.com/uploads/telegram-png/telegram-software-wikipedia-2.png",
    url: "https://t.me/ra_mizu",
    alt: "telegram",
  },
  {
    name: "github",
    icon: "https://imgs.search.brave.com/np-NaC0N3gBsHZTYs6VaesbSU5ZQTfcZ-SAea-uqIb4/rs:fit:860:0:0:0/g:ce/aHR0cHM6Ly9hc3Nl/dHMuc3RpY2twbmcu/Y29tL2ltYWdlcy81/ODQ3Zjk4ZmNlZjEw/MTRjMGI1ZTQ4YzAu/cG5n",
    url: "https://github.com/yoriichii?tab=repositories",
    alt: "github",
  },
]);

const styleIcon = {
  height: "3rem",
};

const timelineEventsEdcuation = ref([
  {
    title: "High School Diploma, Borey 100 Knong High School",
    description: "December 2020",
  },
  {
    title: "Bachelor of Information Technology, Royal University of Phnom Penh",
    description: "May 2024",
  },
]);

const timelineEventsWork = ref([
  {
    title: "Junior Front-End Developer at Ecoinsoft Solution",
    description: "April 2024 - Present",
  },
]);

const skills = [
    { name: 'Vue', logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vuejs/vuejs-original.svg' },
    { name: 'Angular', logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/angularjs/angularjs-original.svg' },
    { name: 'Javascript', logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg' },
    { name: 'Typescript', logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/typescript/typescript-original.svg' },
    { name: 'Git', logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg' },
    { name: 'Github', logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg' },
    { name: 'HTML', logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg' },
    { name: 'CSS', logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg' },
    { name: 'SCSS', logo: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/sass/sass-original.svg' },
    { name: 'Tailwind CSS', logo: tailwindLogo },
  ];
  
</script>

<style scoped></style>
