<template>
  <v-autocomplete
    v-model="select"
    v-model:search="search"
    :loading="loading"
    :items="items"
    class="mx-4"
    density="comfortable"
    hide-no-data
    hide-details
    label="Search course"
    style="max-width: 300px"
  ></v-autocomplete>
  <p>{{this.select}}</p>
</template>

<script lang="ts">
export default {
  data() {
    return {
      loading: false,
      items: [],
      search: null,
      select: null,
      courses: [
        "CS-UH 1001 Introduction to Computer Science",
        "ANTH-UH 2113 Memoir and Ethnography: Understanding Culture Through First-Person Narrative",
        "CCEA-UH 1062 Everything is a Remix",
      ],
    };
  },
  watch: {
    search(val) {
      val && val !== this.select && this.querySelections(val);
    },
  },
  methods: {
    querySelections(v) {
      this.loading = true;
      // Simulated ajax query
      setTimeout(() => {
        this.items = this.courses.filter((e) => {
          return (e || "").toLowerCase().indexOf((v || "").toLowerCase()) > -1;
        });
        this.loading = false;
      }, 500);
    },
  },
};
</script>
