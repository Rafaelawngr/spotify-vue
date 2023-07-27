<script>

  export default {
    name: 'headerComponent',
    emits: [
      "goBackClick"
    ],

    setup(_, {emit}) {
      const goBack = () => {
      emit ("goBackClick")
    }    
    return {
      goBack
    }

    }
  };
 
</script>

<template>

  <div class="header">
    <div class="arrows">
      <button class="material-symbols-outlined" @click="goBack">chevron_left</button>
      <button class="material-symbols-outlined">chevron_right</button>
    </div>

    <div class="profile-pic">
     <img src="https://avatars.githubusercontent.com/u/107516309?v=4" alt="">
</div>
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

.profile-pic img {
  margin-right: 10px;
  width: 35px;
  height: 35px;
  border-radius: 50%;
  border: 3px solid var(--sideMenuColor);
  cursor: pointer;
}
</style>
