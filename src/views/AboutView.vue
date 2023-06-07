<template>
  <div>
    <h2>About View</h2>
    <p>{{ receivedMessage }}</p>
  </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from "vue";
import moment from "moment";
export default defineComponent({
  name: "AboutView",
  props: {
    receivedMessage: {
      type: String as PropType<string>,
      required: true,
    },
  },
  mounted() {
    const now = moment();
    console.log(now.format("YYYY-MM-DD"));
  },
});
</script>
