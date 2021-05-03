<template>
  <div class="app">
    <header>
      <div class="order">
        <button @click="handleClick('title')">Order By Title</button>
        <button @click="handleClick('salary')">Order By Salary</button>
        <button @click="handleClick('location')">Order By Location</button>
      </div>
    </header>

    <JobList :jobs="jobs" :order="order" />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import JobList from "./components/JobsList.vue";
import Job from "./types/Job";
import OrderTerm from "./types/OrderTerm";

export default defineComponent({
  name: "App",
  components: { JobList },
  setup() {
    //Comments are just just  old examples while learning TS
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

    const order = ref<OrderTerm>("title");

    const handleClick = (term: OrderTerm) => {
      order.value = term;
    };
    return { jobs, handleClick, order };
  },

  //Comments are just just  old examples while learning TS
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

<style>
header {
  text-align: center;
}
header .order {
  margin-top: 20px;
}
button {
  margin: 0 10px;
  color: #1195c9;
  border: 3px solid #1195c9;
  background: #d5f0ff;
  padding: 8px 16px;
  border-radius: 4px;
  cursor: pointer;
  font-weight: bold;
}
</style>
