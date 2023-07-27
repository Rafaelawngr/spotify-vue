<script setup>

</script>

<template>

  <div class="header">
  <div class="arrows">
    <button class="material-symbols-outlined">chevron_left</button>
    <button class="material-symbols-outlined">chevron_right</button> 
  </div>

    <button class="profile-pic"> 
      <img src="https://www.pngkey.com/png/full/349-3499617_person-placeholder-person-placeholder.png" alt=""> </button>
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
  background: linear-gradient(180deg, rgba(56, 56, 56, 0.60) 0%, rgba(64, 64, 64, 0.00) 100%);
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

.profile-pic img{
 width: 25px;
}
</style>
