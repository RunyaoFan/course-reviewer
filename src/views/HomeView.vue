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
          <SearchBar />
        </v-col>
        <v-divider vertical></v-divider>
        <v-col cols="12" sm="4">
          <MainOption
            :mainMsg="mainMsg2"
            :subMsg="subMsg2"
            :iconClass="icon2"
          />
          <PurpleButton :text="button1txt" />
        </v-col>
        <v-divider vertical></v-divider>
        <v-col cols="12" sm="4">
          <MainOption
            :mainMsg="mainMsg3"
            :subMsg="subMsg3"
            :iconClass="icon3"
          />
          <PurpleButton :text="button2txt" />
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import MainOption from "@/components/MainOption.vue"; // @ is an alias to /src
import PurpleButton from "@/components/PurpleButton.vue";
import SearchBar from "@/components/SearchBar.vue";

export default defineComponent({
  name: "HomeView",
  components: {
    MainOption,
    PurpleButton,
    SearchBar,
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
        "Kinda works like RoR, with some extra features that could be helpful.",
      button1txt: "Start a new review",
      button2txt: "Start a new post",
    };
  },
});
</script>

<!-- <style>
.main-divider {
  border-width: 1px !important;
  border-color: black !important;
}
</style> -->
