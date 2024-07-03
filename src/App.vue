<script setup>
import { ref, reactive } from "vue";
import HelloWorld from "./components/HelloWorld.vue";

const count = ref(0);
const text= ref("");
const state = reactive({
  count,
});

text.value = 'a'

const handleUp = () => {
  count.value++;
};

const handleDown = () => {
  count.value--;
};

const handleNoti = (value) => {
  console.log(count.value, value);
}
</script>

<template>
  <div id="app">
    {{ count }}
    <hello-world :count="count" :noti.sync="count"/>
    <button type="button" @click="handleUp">버튼</button>
    <button type="button" @click="handleDown">버튼</button>
    <!-- <input :value="text" @update:value="handleChangeText" > -->
  </div>
</template>
