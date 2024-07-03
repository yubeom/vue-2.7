<script setup>
import { computed, reactive, defineEmits } from "vue";

const props = defineProps(["count","noti"]);
const emit = defineEmits(["update:noti"]);

const state = reactive({
  message: computed(() => {
    if (props.count == 0) {
      return "0";
    }

    return props.count > 0 ? "양수" : "음수";
  }),
});

const handleInput = (event) => {
  emit("update:noti", event.target.value);
  console.log(props.noti)
}
</script>

<template>
  <div>
    <h1>카운트: {{ props.count }}</h1>
    <p>{{ state.message }}</p>
    <input type="text" @input="handleInput" :value="props.count" />
  </div>
</template>
