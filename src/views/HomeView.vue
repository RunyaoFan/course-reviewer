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
          <!-- <PurpleButton :text="button1txt" /> -->
          <v-dialog v-model="dialog" width="1024">
            <template v-slot:activator="{ props }">
              <PurpleButton :text="button1txt" v-bind="props" />
              <!-- <v-btn color="primary" v-bind="props"> Open Dialog </v-btn> -->
            </template>
            <v-card class="d-flex align-center justify-center">
              <v-card-title>
                <v-spacer>
                  <span class="text-h5">New Review</span>
                </v-spacer>
              </v-card-title>
              <v-card-text>
                <v-container>
                  <v-row>
                    <v-col cols="6">
                      <p>Course Number (e.g. CS-UH 1001)</p>
                    </v-col>
                    <v-col cols="6">
                      <v-text-field required></v-text-field>
                    </v-col>
                    <v-col cols="6">
                      <p>Professor</p>
                    </v-col>
                    <v-col cols="6">
                      <v-text-field required></v-text-field>
                    </v-col>
                    <v-col cols="6">
                      <p>Semester</p>
                    </v-col>
                    <v-col cols="6">
                      <v-select
                        :items="[
                          'Spring 2023',
                          'Fall 2022',
                          'Spring 2022',
                          'Fall 2021',
                          'Spring 2021',
                          'Fall 2020',
                          'Spring 2020',
                          'Fall 2019',
                          'Spring 2019',
                          'Fall 2018',
                          'Spring 2018',
                          'Fall 2017',
                          'Spring 2017',
                          'Fall 2016',
                        ]"
                      ></v-select>
                    </v-col>
                    <v-col cols="6">
                      <p>Rating</p>
                    </v-col>
                    <v-col cols="6">
                      <div class="text-center">
                        <v-rating
                          v-model="rating"
                          bg-color="orange-lighten-1"
                          color="blue"
                        ></v-rating>
                      </div>
                    </v-col>
                    <v-col cols="6">
                      <p>Upload Syllabus (optional)</p>
                    </v-col>
                    <v-col cols="6">
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
      dialog: false,
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
      newReviewBtnTxt: "Submit",
      rating: 0,
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
