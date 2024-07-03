<script setup>
import { computed, reactive } from "vue";

const props = defineProps(["count"]);

// console.log(props.count);

const state = reactive({
  message: computed(() => {
    if (props.count == 0) {
      return "0";
    }

    return props.count > 0 ? "양수" : "음수";
  }),
});
</script>

<template>
  <div>
    <h1>카운트: {{ props.count }}</h1>
    <p>{{ state.message }}</p>
  </div>
</template>
