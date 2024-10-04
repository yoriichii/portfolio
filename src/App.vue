<template>
  
  <div class="flex flex-col min-h-[100vh]">
    <div>
      <sidebar />
      <div class="absolute top-5 right-4">
    <darkModeToggleVue/>
  </div>
    </div>
    <div class="flex-1">
      <router-view></router-view>
    </div>
    <footerVue />
  </div>
  
</template>

<script setup>
import sidebar from "./components/sidebar.vue";
import footerVue from "./components/footer.vue";
import darkModeToggleVue from "./components/dark-mode-toggle.vue";

</script>

<style scoped>
.footer {
  margin-top: auto;
}
</style>
