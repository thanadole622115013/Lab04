<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import { useMessageStore } from './stores/message';
import { storeToRefs } from 'pinia';
const store = useMessageStore()
const { message } = storeToRefs(store)
</script>

<template>
  <header class="max-h-screen leading-normal">
   
      <nav class="p-8">
        <RouterLink :to="{name: 'EventList'}">Home</RouterLink>
        |
        <RouterLink :to="{name: 'about'}">About</RouterLink>
        |
        <RouterLink :to="{name: 'EventList2'}">New List</RouterLink>
        |
        <RouterLink :to="{name: 'student'}">Student</RouterLink>
      </nav>
      <div id="flashMessage" v-if="message">
      <h4 class="text-xl">{{ message }}</h4></div>
  </header>

  <RouterView />
</template>

<style scoped>
#app{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

/* nav{
  padding: 30px;
} */
nav a{
  font-weight: bold;
  color: #2c3e50;
}
nav a.router-link-exact-active{
  color: #42b983;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
/* h4 {
  font-size: 20px;
} */

@keyframes yellowfade {
  from {
    background: yellow;
  }
  to {
    background: transparent;
  }
}
#flashMessage {
  animation: yellowfade 3s ease-in-out;
}
</style>
