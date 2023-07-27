<script>

import {ref} from "vue";

export default {
  name: 'sideMenuComponent',

  setup() {
    const isClicked = ref(false);

    const toggleSearch = () => {
      isClicked.value = !isClicked.value;
    };

    return {
      isClicked,
      toggleSearch
    }
  }
};

</script>

<template>
  <div class="menu">
    <div class="menu-options">
      <ul>
        <li>
          <button class="menu-options-item"><span class="material-symbols-outlined">home</span>
            Início
          </button>
        </li>
        <li>
          <button class="menu-options-item" :class="{ clicked: isClicked }"  @click="toggleSearch"><span class="material-symbols-outlined">search</span>
            {{ isClicked? "Buscar em sua biblioteca" : "Buscar" }}
          </button>
        </li>
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
  padding: 0 10px;
  color: var(--fontColorSmall);
}


.material-symbols-outlined {
  font-variation-settings: 'FILL' 1,
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
  padding: 8px;
}

button {
  background: none;
  border: none;
  font-size: 1.05rem;
  font-weight: 600;
  color: var(--fontColorSmall);
}


.clicked {
  background-color: #2A2A2A;
  padding: 5px 50px 5px 10px;
  color: #a4a4a4;
  font-size: .8rem;
  width: 100%;
  font-weight: 400;
  border-radius: 10px;
  gap: 5px;
}

.clicked:hover {
  transform: none;
}

</style>
