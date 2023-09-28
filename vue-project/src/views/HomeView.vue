<script setup>
import { RouterLink } from 'vue-router';
</script>

<template>
  <main>
    <section class="home-page">
      <div class="intro-container">
        <div class="section-title">
          <h1>Hello and Welcome</h1>
        </div>

        <div class="text-container">
          <p>
            This is my portfolio website. It contains previous projects that I have worked on for this unit.<br>
            Feel free to look around and if you want, use my projects as a template or reference to create your own.
          </p>
        </div>
      </div>

      <div class="links-container">
        <RouterLink to="projects">View Projects</RouterLink>
      </div>
    </section>
  </main>
</template>
