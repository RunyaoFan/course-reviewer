<template>
  <div class="main-option">
    <i :class="iconClass" style="font-size: 4em;"></i>
    <h3 class="red--text">{{ mainMsg }}</h3>
    <p>{{ subMsg }}</p>
     
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "MainOption",
  props: {
    iconClass: String,
    mainMsg: String,
    subMsg: String,
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500&display=swap');
@import url("https://cdn-uicons.flaticon.com/uicons-regular-rounded/css/uicons-regular-rounded.css");
h3 {
  /* margin: 40px 0 0; */
  font-family: 'Montserrat', sans-serif;
  font-size: 40px;
  font-weight: 500;
}
p {
  margin:auto;
  font-family: 'Montserrat', sans-serif;
  font-weight: 500;
  width: 80%;
}
.main-option {
    text-align: center;
}
/* ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
} */
</style>
