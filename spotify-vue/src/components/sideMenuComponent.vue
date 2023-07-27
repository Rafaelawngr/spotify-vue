<script setup>

</script>

<template>
  <div class="menu">
  <div class="menu-options">
    <ul>
      <li class="menu-options-item"><span class="material-symbols-outlined">
home
</span>Início</li>
      <li class="menu-options-item"><span class="material-symbols-outlined">
search
</span>Buscar</li>
    </ul>
  </div>
  </div>
</template>

<style scoped>

  .menu {
    display: flex;
    align-items: center;
    background: var(--sideMenuColor);
    width: 100%;
    height: 100%;
    border-radius: 10px;
    grid-area: side1;
  }
  
  .menu-options {
    padding: 10px;
    font-weight: 600;
    color: var(--fontColorSmall);
  }
  

  .material-symbols-outlined {
    font-variation-settings:
        'FILL' 0,
        'wght' 400,
        'GRAD' 0,
        'opsz' 24;
  }
  
  .menu-options-item {
    display: flex;
    align-items: center;
    gap: 15px;
    transition: 500ms;
  }
  
  .menu-options-item:hover {
    transform: scale(1.05);
    color: var(--fontColorTitle)
  }
  
  li {
    list-style: none;
    padding: 10px;
  }
  

  
</style>
