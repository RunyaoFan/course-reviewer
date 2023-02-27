<template>
  <v-dialog v-model="dialog" width="768">
    <template v-slot:activator="{ props }">
      <PurpleButton :text="button1txt" v-bind="props" />
    </template>
    <v-card class="d-flex align-center justify-center new-review-card">
      <v-card-title>
        <v-spacer>
          <span class="text-h5 window-title">New Review</span>
        </v-spacer>
      </v-card-title>
      <v-card-text>
        <v-container>
          <v-row class="d-flex align-center">
            <v-col cols="12" sm="7" >
              <p class="prompt">Course Number (e.g. CS-UH 1001)</p>
            </v-col>
            <v-col cols="12" sm="5">
              <v-text-field required variant="underlined"></v-text-field>
            </v-col>
            <v-col cols="12" sm="7">
              <p>Professor</p>
            </v-col>
            <v-col cols="12" sm="5">
              <v-text-field required variant="underlined"></v-text-field>
            </v-col>
            <v-col cols="12" sm="7">
              <p>Semester</p>
            </v-col>
            <v-col cols="12" sm="5">
              <v-select variant="underlined" :items="items"></v-select>
            </v-col>
            <v-col cols="12" sm="7">
              <p>Rating</p>
            </v-col>
            <v-col cols="12" sm="5">
              <div class="text-center">
                <v-rating
                  v-model="rating"
                  bg-color="orange-lighten-1"
                  color="blue"
                ></v-rating>
              </div>
            </v-col>
            <v-col cols="12" sm="7">
              <p>Upload Syllabus (optional)</p>
            </v-col>
            <v-col cols="12" sm="5">
              <v-file-input label="File input" variant="solo"></v-file-input>
            </v-col>
          </v-row>
        </v-container>
      </v-card-text>
      <v-card-actions>
        <v-spacer></v-spacer>
        <PurpleButton :text="newReviewBtnTxt" />
      </v-card-actions>
    </v-card>
  </v-dialog>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import PurpleButton from "./PurpleButton.vue";

export default defineComponent({
  name: "NewReview",
  components: {
    PurpleButton,
  },
  data() {
    return {
      dialog: false,
      newReviewBtnTxt: "Submit",
      rating: 0,
      button1txt: "Start a new review",
      items: [
        "Spring 2023",
        "Fall 2022",
        "Spring 2022",
        "Fall 2021",
        "Spring 2021",
        "Fall 2020",
        "Spring 2020",
        "Fall 2019",
        "Spring 2019",
        "Fall 2018",
        "Spring 2018",
        "Fall 2017",
        "Spring 2017",
        "Fall 2016",
      ],
    };
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600&display=swap");
p {
  font-family: "Montserrat", sans-serif;
  font-weight: 600;
}
.window-title {
  font-family: "Montserrat", sans-serif !important;
  font-weight: 600;
}

.new-review-card {
  padding: 30px 1px;
}

/* .prompt {
  margin: 0px;
} */
</style>
