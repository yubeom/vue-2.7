<script setup>
import { ref, reactive } from "vue";
import HelloWorld from "./components/HelloWorld.vue";

const count = ref(0);
const state = reactive({
  count,
});

const handleUp = () => {
  count.value++;
};

const handleDown = () => {
  count.value--;
};
</script>

<template>
  <div id="app">
    <hello-world :count="count" />
    <button type="button" @click="handleUp">버튼</button>
    <button type="button" @click="handleDown">버튼</button>
  </div>
</template>
