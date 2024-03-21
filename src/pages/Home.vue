<template>
  <img
    src="/Sims_4_logo.svg"
    alt="The Sims 4"
    class="center"
    style="height: 100%; width: 400px"
  />

  <button
    @click="
      showImage = true;
      randomize_basic();
    "
    class="button"
  >
    Create a Sim
  </button>
  <br />

  <div
    v-if="showImage"
    class="center"
    style="
      background-color: #b2cedeff;
      width: 470px;
      padding: 9px 5px 1px 5px;
      border-radius: 5px;
    "
  >
    <img src="/species/alien_green.svg" alt="alien" srcset="" />
    <img src="/species/vampire.svg" alt="alien" srcset="" />
    <img src="/species/mermaid.svg" alt="alien" srcset="" />
    <img src="/species/spellcaster.svg" alt="alien" srcset="" />
    <img src="/species/werewolf.svg" alt="alien" srcset="" />
  </div>
  <div
    v-if="showImage"
    class="center"
    style="
      background-color: #b2cedeff;
      width: 470px;
      padding: 9px 5px 1px 5px;
      border-radius: 5px;
    "
  >
    <div class="gutter" style="">
      <div style="display: inline; vertical-align: middle">
        <img :src="gender_path" alt="gender" srcset="" />
      </div>

      <div style="display: inline; vertical-align: middle">
        <img src="/age.svg" alt="age" srcset="" />
      </div>

      <div style="display: inline; vertical-align: middle">
        <img src="/default_walk.svg" alt="walk" srcset="" />
      </div>

      <div style="display: inline; vertical-align: middle">
        <img :src="voice_path" alt="voice" srcset="" />
      </div>

      <div style="display: inline; vertical-align: middle">
        <img src="/relationships.svg" alt="relationships" srcset="" />
      </div>
    </div>
  </div>
  <p style="margin: auto; width: fit-content">
    Voice level is: {{ voice_level }}
  </p>
  <br />
</template>

<script setup>
import { computed, ref } from "vue";

const showImage = ref(false);

const genders = ["female", "male"];
const voices = ["sweet", "melodic", "lilted", "clear", "warm", "brash"];

const gender = ref(genders[0]);
const voice = ref(voices[0]);

const gender_path = computed(() => "/" + gender.value + ".svg");
const voice_path = computed(() => "/" + voice.value + ".svg");
const voice_level = ref(0);

function randomize_basic() {
  gender.value = genders[Math.floor(Math.random() * genders.length)];
  voice.value = voices[Math.floor(Math.random() * voices.length)];
  voice_level.value = Math.random() * 10;
}
</script>
