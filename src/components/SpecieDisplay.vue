<template>
  <div
    style="
      background-color: #b2cedeff;
      width: 470px;
      padding: 9px 5px 1px 5px;
      border-radius: 5px;
    "
  >
    <img :src="human_path" alt="human" srcset="" />
    <img :src="alien_path" alt="alien" srcset="" />
    <img :src="vampire_path" alt="vampire" srcset="" />
    <img :src="mermaid_path" alt="mermaid" srcset="" />
    <img :src="spellcaster_path" alt="spellcaster" srcset="" />
    <img :src="werewolf_path" alt="werewolf" srcset="" />
  </div>
</template>

<script setup>
import { computed, ref } from "vue";
const props = defineProps({
  specie: {
    type: String,
    required: true,
  },
});

const human_path = computed(() =>
  props.specie === "human" ? "/species/human_green.svg" : "/species/human.svg"
);

const alien_path = computed(() =>
  props.specie === "alien" ? "/species/alien_green.svg" : "/species/alien.svg"
);

const mermaid_path = computed(() =>
  props.specie === "mermaid"
    ? "/species/mermaid_green.svg"
    : "/species/mermaid.svg"
);

const spellcaster_path = computed(() =>
  props.specie === "spellcaster"
    ? "/species/spellcaster_green.svg"
    : "/species/spellcaster.svg"
);

const vampire_path = computed(() =>
  props.specie === "vampire"
    ? "/species/vampire_green.svg"
    : "/species/vampire.svg"
);

const werewolf_path = computed(() =>
  props.specie === "werewolf"
    ? "/species/werewolf_green.svg"
    : "/species/werewolf.svg"
);
</script>

<style scoped></style>
