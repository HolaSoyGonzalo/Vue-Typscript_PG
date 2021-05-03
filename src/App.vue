<template>
  <div class="app">
    <JobList :jobs="jobs" />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import JobList from "./components/JobsList.vue";
import Job from "./types/Job";

export default defineComponent({
  name: "App",
  components: { JobList },
  setup() {
    // const state = reactive({
    //   name: "Gonzalo",
    //   age: 26 as string | number,
    // });
    // state.name = "Peck";
    // return { ...toRefs(state) };
    // const name = ref("Gonzalo");
    // const age = ref<number | string>(25);

    // return { name, age };

    const jobs = ref<Job[]>([
      { title: "JS Developer", location: "Milan", salary: 100, id: "1" },
      { title: "Simple Worker", location: "Rome", salary: 200, id: "2" },
      { title: "Average Worker", location: "Naples", salary: 300, id: "3" },
      { title: "Hard Worker", location: "Venice", salary: 400, id: "4" },
      { title: "Workaholic", location: "Bergamo", salary: 500, id: "5" },
    ]);
    return { jobs };
  },

  // methods: {
  //   changeName(name: string) {
  //     this.name = name;
  //     return name;
  //   },
  //   changeAge(age: string | number) {
  //     this.age = age;
  //     return age;
  //   },
  // },
});
</script>

<style></style>
