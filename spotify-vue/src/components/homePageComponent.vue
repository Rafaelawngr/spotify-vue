<script setup>

import HeaderComponent from "./headerComponent.vue";
import LastPlayedComponent from "./LastPlayedComponent.vue";
import ForYouComponent from "./ForYouComponent.vue";
</script>

<template>
  <main>
    <HeaderComponent/>
    <LastPlayedComponent />
    <ForYouComponent />
    <h2>Feitos para você</h2>
    <ForYouComponent />
  </main>
</template>

<style scoped>

main {
  display: flex;
  flex-direction: column;
  width: 100%;
  max-height: 770px;
  padding: 10px;
  grid-area: main;
  border-radius: 10px;
  background: linear-gradient(360deg, #121212 14.84%, #232323 70.76%, #404040 100%);
  overflow: scroll;
}

main::-webkit-scrollbar {
  width: 5px;
  height: 100px;
  background: transparent;

}

main::-webkit-scrollbar-track {
  background: transparent;
  border-radius: 2px;
}

main::-webkit-scrollbar-thumb {
  background: #575757;
  border-radius: 5px;
}

h2 {
  margin-top: 20px;
  color: var(--fontColorTitle);
  padding: 10px;
  font-size: 1.15rem;
}
</style>