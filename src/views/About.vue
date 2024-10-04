<template>
  <div class="flex flex-col items-center px-4 py-24"> 
    <section class="w-[90%] md:max-w-md xl:max-w-2xl mx-auto -z-10">
      <span v-if="loading" class="loading loading-spinner text-primary relative left-[48.5%] w-8"></span>
      <div v-else
        class="group relative flex size-full overflow-hidden rounded-xl bg-white-100 dark:bg-neutral-900 text-black-800 dark:text-white shadow-2xl p-5 border border-purple-500"
      >

        <div>
          <h1 class="text-purple-500 text-2xl">Hey</h1>
          <p class="mt-3">
            Hello! I'm Dara, a front-end developer driven by a love for coding
            and a deep interest in emerging technologies. My journey is fueled
            by a constant curiosity to explore new tools, frameworks, and
            programming languages, allowing me to craft creative and efficient
            solutions. I thrive on tackling challenging problems and have honed
            my skills through diverse projects that push the boundaries of
            what's possible.
          </p>
          <h2>My Passion for Technology</h2>
          <p>
            My passion for coding goes beyond just writing lines of code; it's
            about the thrill of creating something meaningful from scratch and
            solving problems in innovative ways. I love the process of turning
            ideas into reality through code, where every project is an
            opportunity to learn, grow, and refine my skills. Whether it's
            mastering a new framework or debugging a tricky piece of code, I
            find immense satisfaction in the journey of continuous improvement.
          </p>
          <h2>Professional Experience</h2>
          <p>
            My professional journey I have had the opportunity to work on
            projects ranging from web development with a solution company and
            worked with project of Ministry of Environment as a junior
            developer, and I learn alot of such as knowing how to debugging
            code, integration with API etc.
          </p>
          <h2>Skills and Expertise</h2>
          <p>
            Throughout my career, I have honed a broad set of skills that enable
            me to tackle a wide range of technical challenges:
          </p>
          <p>- Languages : Experienced with JavaScript, TypeScript.</p>
          <p>- Framework : such as Angular and Vue 3.</p>
          <p>
            - Tool : Skilled in using Git, Github, Gitea, ClickUp and figma.
          </p>
          <h2>Lets Connect</h2>
          <p>
            I'm always eager to connect with fellow tech enthusiasts who share a
            passion for innovation and creativity. Whether it's exchanging
            ideas, exploring new technologies, or collaborating on impactful
            projects, I believe great things happen when like-minded individuals
            come together. Let's connect on my social or by an email—let's push
            the boundaries of technology and shape the future together.
          </p>
          <div class="flex gap-5 mt-4">
            <img src="../assets/email.png" alt="email" />
            <span>puthsovannara@gmail.com</span>
          </div>
          <div class="flex gap-5 mt-4">
            <img src="../assets/phone.png" alt="phone" />
            <span>+855 967959819</span>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
import { ref, onMounted } from "vue";

const loading = ref(true);
onMounted(()=>{
  setTimeout(() =>{
  loading.value = false;
},1000)
})



</script>

<style scoped>
h2 {
  margin-top: 1rem;
  color: #a855f7;
  font-size: 1.1rem;
  line-height: 2rem;
  font-weight: 500;
}

p {
  margin-top: 1rem;
}

</style>
