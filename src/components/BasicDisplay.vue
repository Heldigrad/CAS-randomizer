<template>
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
</template>

<script setup>
import { computed, ref } from "vue";
const props = defineProps({
  gender: {
    type: String,
    required: true,
  },
  voice: {
    type: String,
    required: true,
  },
});

const gender_path = computed(() => "/" + props.gender + ".svg");
const voice_path = computed(() => "/" + props.voice + ".svg");
</script>

<style scoped></style>
