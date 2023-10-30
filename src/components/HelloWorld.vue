<script setup>
import {ref} from "vue"
const props = defineProps({
  start: {
    type: String,
    required: true
  },
  hello : {
    type: String,
    required: true
  }
})
const isClicked = ref(false)
const changeText = () => isClicked.value = !isClicked.value
</script>

<template>
  <div class="greetings">
    <h1 class="green">{{ isClicked ? props.hello : props.start }}</h1>
    <button @click="changeText">{{ isClicked ? props.start : props.hello }}</button>
    <h3>
      You’ve successfully created a project with
      <a href="https://vitejs.dev/" target="_blank" rel="noopener">Vite</a> +
      <a href="https://vuejs.org/" target="_blank" rel="noopener">Vue 3</a>.
    </h3>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

button {
  background-color: #41B883; 
  color: #fff;
  padding: 10px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-family: Inter, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Fira Sans', 'Droid Sans', 'Helvetica Neue', sans-serif;
}
.greetings {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  }

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {

  .greetings {
  align-items: flex-start;
}
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
