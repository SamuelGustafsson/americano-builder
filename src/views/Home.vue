<template>
  <InputText type="text" v-model="inputPlayerName" @keydown.enter="addPlayer" />
  <ul>
    <li v-for="player in players" :key="player">{{ player }}</li>
  </ul>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import InputText from "@/components/InputText.vue";

export default defineComponent({
  name: "Home",
  components: {
    InputText
  }
});
</script>
