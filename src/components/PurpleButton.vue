<template>
  <button>{{ text }}</button>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "PurpleButton",
  props: {
    text: String,
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600&display=swap');
button {
  font-family: 'Montserrat', sans-serif;
  background-color: #7B5AA6;
  color: #FFFFFF;
  padding: 10px 20px;
  border-radius: 40px;
  font-weight: 600;
  font-size: 1em;
}

button:hover {
  background-color: #57068C;
}
</style>
