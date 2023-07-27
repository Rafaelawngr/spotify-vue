<script>
  import LastPlayedComponent from "./LastPlayedComponent.vue";
  import ForYouComponent from "./ForYouComponent.vue";

  export default {
    name: 'headerComponent',
    
    setup() {
   
      
      let selectedImage;
      let previewFile;
      let file;
      let reader = new FileReader();
      
      reader.onloadend = () => {
        previewFile.src = reader.result;
        selectedImage = reader.result;
      };
      
      
    return {
      // changePic
    }
    }
  }
</script>

<template>

  <div class="header">
    <div class="arrows">
      <button class="material-symbols-outlined">chevron_left</button>
      <button class="material-symbols-outlined">chevron_right</button>
    </div>

    <button @click="changePic" class="profile-pic">
      <img src="https://www.pngkey.com/png/full/349-3499617_person-placeholder-person-placeholder.png" alt=""></button>
  </div>

</template>

<style scoped>

.header {
  position: sticky;
  top: 0;
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  height: 8%;
  background: linear-gradient(180deg, rgba(56, 56, 56, 0.70) 0%, rgba(64, 64, 64, 0.10) 100%);
}

.arrows {
  display: flex;
  flex-direction: row;
  gap: 10px;
  padding: 15px;
}

.material-symbols-outlined {
  color: var(--fontColorSmall);
  background: var(--sideMenuColor);
  border: none;
  cursor: pointer;
  border-radius: 50%;
  font-weight: 200;
  font-size: 25px;
}

.profile-pic {
  margin-right: 10px;
  width: 30px;
  height: 30px;
  border-radius: 50%;
  border: 2px solid rgba(49, 49, 49, 0.53);
}

.profile-pic img {
  width: 25px;
}
</style>
