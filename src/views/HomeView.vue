<template>
  <div class="app">
    <p>{{ name }} - {{ age }}</p>
    <button @click="changeName('heet')">change name</button>
    <button @click="changeAge(87)">change age</button>
    <AboutView :receivedMessage="message" />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import AboutView from "./AboutView.vue";
const age = 1;
interface User {
  name: string;
  age: number;
  email: string;
}

export default defineComponent({
  name: "App",
  components: {
    AboutView,
  },
  props: { receivedMessage: { type: String, required: true } },

  data() {
    return {
      message: "Hello how are you?" as string,
      name: "Bhumik",
      user: {} as User,
      // users: [] as User[],
      age: 22 as number | string,
    };
  },
  methods: {
    changeName(name: string) {
      this.name = name;
    },
    changeAge(age: number | string) {
      this.age = age;
      return age;
    },
  },
  mounted() {
    // this.name = 23
  },
});
</script>

<style></style>
