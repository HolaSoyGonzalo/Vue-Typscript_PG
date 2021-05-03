<template>
  <div class="app">
    <p>{{ name }} - {{ age }}</p>
    <button @click="changeName('Gus')">Change Name</button>
    <button @click="changeAge('28')">Change Age</button>
  </div>
</template>

<script lang="ts">
// let age: string | number = 25;

import { defineComponent, reactive, toRefs, ref } from "vue";

export default defineComponent({
  name: "App",
  components: {},
  setup() {
    // const state = reactive({
    //   name: "Gonzalo",
    //   age: 26 as string | number,
    // });
    // state.name = "Peck";
    // return { ...toRefs(state) };

    const name = ref("Gonzalo");
    const age = ref<number | string>(25);

    return { name, age };
  },

  methods: {
    changeName(name: string) {
      this.name = name;
      return name;
    },
    changeAge(age: string | number) {
      this.age = age;
      return age;
    },
  },
});
</script>

<style></style>
