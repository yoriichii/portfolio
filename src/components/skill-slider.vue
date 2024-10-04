<template>
    <div class="w-full max-w-4xl mx-auto p-2">
      <h2 class="text-3xl font-bold mb-16 text-center underline">Skills</h2>
      <div 
        class="overflow-hidden" 
        @mouseenter="pauseAnimation" 
        @mouseleave="resumeAnimation"
      >
        <div 
          class="animate-scroll" 
          :class="{ 'paused': isPaused }"
        >
          <!-- Render the skills twice for infinite scroll -->
          <div 
            v-for="(skill, index) in skills" 
            :key="`original-${index}`"
            class="flex-shrink-0 w-32 h-32 m-2 bg-gray-800 rounded-lg shadow-md flex flex-col items-center justify-center p-2 skill-item"
          >
            <img :src="skill.logo" :alt="skill.name" class="w-12 h-12 mb-2" />
            <span class="text-sm text-center text-white">{{ skill.name }}</span>
          </div>
  
          <!-- Duplicate skill items to create a continuous scroll effect -->
          <div 
            v-for="(skill, index) in skills" 
            :key="`duplicate-${index}`"
            class="flex-shrink-0 w-32 h-32 m-2 bg-gray-800 rounded-lg shadow-md flex flex-col items-center justify-center p-2 skill-item"
          >
            <img :src="skill.logo" :alt="skill.name" class="w-12 h-12 mb-2" />
            <span class="text-sm text-center text-white">{{ skill.name }}</span>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  defineProps({
    skills: {
      type: Array,
      required: true
    },
  });
  
  const isPaused = ref(false);
  
  const pauseAnimation = () => {
    isPaused.value = true;
  };
  
  const resumeAnimation = () => {
    isPaused.value = false;
  };
  </script>
  
  <style scoped>
  @keyframes scroll {
    0% {
      transform: translateX(0);
    }
    100% {
      transform: translateX(-50%);
    }
  }
  
  .animate-scroll {
    animation: scroll 30s linear infinite;
    display: flex;
    width: max-content;
  }
  
  .skill-item {
    transition: transform 0.3s ease-in-out;
    cursor: pointer;
  }
  
  .skill-item:hover {
    transform: translateZ(20px) scale(1.1);
    border: 2px solid #9333EA;
  }
  
  .paused {
    animation-play-state: paused;
  }
  
  </style>
  