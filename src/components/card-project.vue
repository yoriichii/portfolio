<template>
  <div class="card">
    <div class="card2">
      <img
        :src="image"
        alt="Project Image"
        class="text-white h-[350px] rounded-md"
        width="460px"
      />
    </div>
  </div>
</template>
<script setup>
defineProps({
  image: {
    type: String,
  },
});
</script>

<style scoped>
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
