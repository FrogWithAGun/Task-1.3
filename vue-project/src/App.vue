<script setup>
  import { RouterLink, RouterView } from 'vue-router'
  import { ref } from 'vue'
  import ButtonCounter from '../src/components/ButtonCounter.vue'

  const menuVisible = ref(false);

  // A function that changes menu visibility as well as the text in the button that activates it
  const changeMenuVisibility = () => {
    menuVisible.value = !menuVisible.value;
    
    if (menuVisible.value == false) {
      document.getElementById('visibility-button').innerText = "Show Menu";
    }

    else {
      document.getElementById('visibility-button').innerText = "Hide Menu";
    }
  }
</script>

<template>
  <div class="page-content">
    <div class="menu-container">
      <div class="button-container">
        <button @click="changeMenuVisibility" id="visibility-button" class="nice-button">Show Menu</button>
      </div>

      <br>

      <div v-if="menuVisible" class="links-container">
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/projects">View Projects</RouterLink>
        <RouterLink to="/about">About Me</RouterLink>
      </div>
    </div>

    <div class="section-content">
      <RouterView></RouterView>
    </div>


    <br><br>

    <div class="button-game-container">
      <ButtonCounter></ButtonCounter>
    </div>
  </div>
</template>