<template>
  <div>
    <h3>{{ greeting }}! Thank you for visiting!</h3>
    <button @click="greeting = randomMessage()">New Greeting</button>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  name: "Greeting",
  props: ["messages"],
  setup(props) {
    const greeting = ref(props?.messages[0]);
    console.log(props.messages);

    function randomMessage() {
      return props.messages[Math.floor(Math.random() * props.messages.length)];
    }

    return {
      greeting,
      randomMessage,
    };
  },
};
</script>

<style scoped></style>
