<template>
  <div class="home">
    <v-container>
      <v-row no-gutters>
        <v-col cols="12" sm="4">
          <MainOption
            :mainMsg="mainMsg1"
            :subMsg="subMsg1"
            :iconClass="icon1"
          />
        </v-col>
        <v-col cols="12" sm="4">
          <MainOption
            :mainMsg="mainMsg2"
            :subMsg="subMsg2"
            :iconClass="icon2"
          />
          <v-btn
            variant="flat"
            rounded="pill"
            color="#7B5AA6"
            class="text-none"
          >
            Start a new review
          </v-btn>
        </v-col>
        <v-col cols="12" sm="4">
          <MainOption
            :mainMsg="mainMsg3"
            :subMsg="subMsg3"
            :iconClass="icon3"
          />
          <v-btn
            variant="flat"
            rounded="pill"
            color="#7B5AA6"
            class="text-none"
          >
            Start a new post
          </v-btn>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import MainOption from "@/components/MainOption.vue"; // @ is an alias to /src

export default defineComponent({
  name: "HomeView",
  components: {
    MainOption,
  },
  data() {
    return {
      icon1: "fi fi-rr-search",
      mainMsg1: "Search",
      subMsg1: "Read course reviews and check out the syllabus (if available).",
      icon2: "fi fi-rr-edit",
      mainMsg2: "Review",
      subMsg2:
        "Share your thoughts on a class. Share the syllabus too if you feel like it.",
      icon3: "fi fi-rr-comment-question",
      mainMsg3: "Request",
      subMsg3:
        "Kinda works like RoR, with some extra features we thought could be helpful.",
    };
  },
});
</script>
