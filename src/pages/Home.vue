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
      randomize_species();
      randomize_basic();
    "
    class="button"
  >
    Create a Sim
  </button>
  <br />

  <specie-display v-if="showImage" class="center" :specie="specie" />

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
    <basic-display
      v-if="showImage"
      class="center"
      :gender="gender"
      :voice="voice"
    />

    <p style="margin: auto; width: fit-content">
      Voice level is: {{ voice_level }}
    </p>
  </div>

  <br />
</template>

<script setup>
import { ref } from "vue";

import SpecieDisplay from "../components/SpecieDisplay.vue";
import BasicDisplay from "../components/BasicDisplay.vue";

const showImage = ref(false);

//*******//
//species//
//*******//

const species = [
  "human",
  "alien",
  "mermaid",
  "spellcaster",
  "vampire",
  "werewolf",
];
const specie = ref(species[0]);

function randomize_species() {
  specie.value = species[Math.floor(Math.random() * species.length)];
}

//*******//
// basic //
//*******//

const genders = ["female", "male"];
const voices = ["sweet", "melodic", "lilted", "clear", "warm", "brash"];
const gender = ref(genders[0]);
const voice = ref(voices[0]);

const voice_level = ref(0);

function randomize_basic() {
  gender.value = genders[Math.floor(Math.random() * genders.length)];
  voice.value = voices[Math.floor(Math.random() * voices.length)];
  voice_level.value = Math.random() * 10;
}
</script>
