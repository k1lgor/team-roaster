<script setup>
import { ref } from "vue";

const teamMembers = ref([
  {
    name: "Jax Cygnus",
    title: "Product Owner",
    img: "jcygnus.webp",
    styleIndex: 1,
  },
  {
    name: "Nyx Vector",
    title: "Tech Lead / Scrum Master",
    img: "nvector.webp",
    styleIndex: 2,
  },
  {
    name: "Kaelen Raze",
    title: "Engineer",
    img: "kraze.webp",
    styleIndex: 0,
  },
  {
    name: "Silas Cortex",
    title: "Engineer",
    img: "scortex.webp",
    styleIndex: 1,
  },
  {
    name: "Orion Flux",
    title: "Engineer",
    img: "oflux.webp",
    styleIndex: 0,
  },
  {
    name: "Vesper Glitch",
    title: "Engineer",
    img: "vglitch.webp",
    styleIndex: 1,
  },
]);

const getImageUrl = (imageName) => {
  return new URL(`../assets/images/${imageName}`, import.meta.url).href;
};

const leaders = teamMembers.value.slice(0, 2);
const engineers = teamMembers.value.slice(2);
</script>

<template>
  <div>
    <div class="container">
      <div class="row">
        <div class="col-sm-6 offset-sm-3 mt-4 mb-6 stack" style="--stack: 3">
          <h2 class="font-name text-center" style="--index: 1">Team Roaster</h2>
          <h2 class="font-name text-center" style="--index: 2">Team Roaster</h2>
          <h2 class="font-name text-center" style="--index: 0">Team Roaster</h2>
        </div>
      </div>

      <div class="row">
        <div class="col-md-6" v-for="member in leaders" :key="member.name">
          <div class="card-box text-center">
            <div class="user-pic">
              <img
                :src="getImageUrl(member.img)"
                class="img-fluid"
                alt="User Pic"
              />
            </div>
            <div class="stack">
              <h4 class="font-name" :style="`--index: ${member.styleIndex}`">
                {{ member.name }}
              </h4>
            </div>
            <h6 class="font-title">{{ member.title }}</h6>
          </div>
        </div>
      </div>

      <div class="row">
        <div class="col-md-3" v-for="member in engineers" :key="member.name">
          <div class="card-box text-center">
            <div class="user-pic">
              <img
                :src="getImageUrl(member.img)"
                class="img-fluid"
                alt="User Pic"
              />
            </div>
            <div class="stack">
              <h4 class="font-name" :style="`--index: ${member.styleIndex}`">
                {{ member.name }}
              </h4>
            </div>
            <h6 class="font-title">{{ member.title }}</h6>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
