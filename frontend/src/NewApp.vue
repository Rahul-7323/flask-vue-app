<script setup>
import { ref } from 'vue';
import CounterButton from "./components/CounterButton.vue";
import ApiMessage from "./components/ApiMessage.vue";
let count = ref(5);
</script>

<template>
    <button @click="count++">increment</button>
    <button @click="count--">decrement</button>
    <ApiMessage/>
    <div>
        <TransitionGroup name="list">
        <CounterButton v-for="i in count" :key="i"></CounterButton>
        </TransitionGroup>
    </div>
</template>

<style>

:root{
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    color: rgb(59, 59, 59);
}

body {
    background: rgb(197, 229, 255);
}

</style>

<style scoped>
 div {
     display: flex;
     flex-flow: row wrap;
     align-items: center;
     justify-content: center;
 }

.list-move, /* apply transition to moving elements */
.list-enter-active,
.list-leave-active {
  transition: all 0.5s ease;
}

.list-enter-from,
.list-leave-to {
  opacity: 0;
  transform: translateX(30px);
}

/* ensure leaving items are taken out of layout flow so that moving
   animations can be calculated correctly. */
.list-leave-active {
  position: absolute;
}
</style>