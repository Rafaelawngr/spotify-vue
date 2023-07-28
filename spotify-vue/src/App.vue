<template>
  <SideMenuComponent/>
  <SideMenuLibraryComponent/>
  <HomePageComponent/>
  <PlayerComponent />
</template>

<script>

import SideMenuComponent from "./components/sideMenuComponent.vue";
import HomePageComponent from "./components/homePageComponent.vue";
import PlayerComponent from "./components/playerComponent.vue";
import SideMenuLibraryComponent from "./components/sideMenuLibraryComponent.vue";

export default {
  name: 'App',
  components: {
    SideMenuComponent,
    HomePageComponent,
    PlayerComponent,
    SideMenuLibraryComponent
  },
  
  setup() {
    
    return {
     
    }
  }
} 
</script>


