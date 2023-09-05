<script setup>
import { useMouse } from "../reusables/mouse.js";
import MyModal from "../components/MyModel.vue";
import { ref } from "vue";

const show = ref(true);

const { x, y } = useMouse();
const items = ref([1, 2, 3, 4, 5]);
function insert() {
  const i = Math.round(Math.random() * items.value.length);
  items.value.splice(i, 0, id++);
}

import Modal from "../components/MyModel.vue";

const showModal = ref(false);

// enables v-focus in templates
const vFocus = {
  mounted: (el) => el.focus(),
};
</script>

<template>
  <h1>Mouse Tracker</h1>
  Mouse position is at: {{ x }}, {{ y }}

  <h1>Transition</h1>
  <button @click="show = !show">Toggle</button>
  <Transition>
    <p v-if="show">hello</p>
  </Transition>

  <div>
    <input v-focus />
  </div>

  <h2>Transition Group</h2>
  <button @click="insert">insert at random index</button>

  <TransitionGroup name="list" tag="ul">
    <li v-for="item in items" :key="item">
      {{ item }}
    </li>
  </TransitionGroup>

  <h1>Teleport</h1>

  <div class="outer">
    <h3>Vue Teleport Example</h3>
    <div>
      <MyModal />
    </div>
  </div>
</template>

<style scoped>
.list-enter-active,
.list-leave-active {
  transition: all 0.5s ease;
}
.list-enter-from,
.list-leave-to {
  opacity: 0;
  transform: translateX(30px);
}
/* we will explain what these classes do next! */
.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
</style>
