<script>

import HeaderComponent from "./headerComponent.vue";
import LastPlayedComponent from "./LastPlayedComponent.vue";
import ForYouComponent from "./ForYouComponent.vue";
import {TYPES} from "../assets/utils";

export default {
  computed: {
    TYPES() {
      return TYPES
    }
  },
  components: {
    HeaderComponent,
    LastPlayedComponent,
    ForYouComponent
  },
  setup() {
    
  return {
   
  };

}
}

</script>

<template>
  <main>
    <HeaderComponent/>
    <LastPlayedComponent />
    <ForYouComponent titulo="Álbuns Recomendados para Você" :type="TYPES.RECOMMENDED"/>
    <ForYouComponent titulo="Os maiores Hits do Momento" :type="TYPES.HITS"/>
    <ForYouComponent titulo="Seus Programas" :type="TYPES.PODCASTS"/>
  </main>
</template>

<style scoped>

main {
  display: flex;
  flex-direction: column;
  width: 100%;
  max-height: 770px;
  grid-area: main;
  border-radius: 10px;
  background: linear-gradient(360deg, #121212 14.84%, #232323 70.76%, #404040 100%);
  overflow-y: scroll;

}

main::-webkit-scrollbar {
  width: 5px;
  background: transparent;
}

main::-webkit-scrollbar-thumb {
  background: #4d4d4d;
  border-radius: 5px;
}

main::-webkit-scrollbar-track {
  margin: 50px;
  padding: 2px;
}

h2 {
  margin-top: 20px;
  color: var(--fontColorTitle);
  padding: 10px;
  font-size: 1.15rem;
}
</style>