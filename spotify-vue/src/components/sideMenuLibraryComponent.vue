<script setup>

</script>

<template>
  <div class="menu-library">
    <h1 class="menu-library-title"><span class="material-symbols-outlined">
import_contacts
</span>Sua Biblioteca</h1>
    <div class="menu-library-items">
      <button>Músicas curtidas</button>
      <button>Radar de Novidades</button>
      <button>Tocadas Recentemente</button>
      <button>Álbuns</button>
      <button>Artistas</button>
      <button>Podcasts</button>
    </div>
  </div>
  <div class="menu-playlists">
  </div>
</template>

<style scoped>

.menu-library {
  display: flex;
  flex-direction: column;
  padding: 10px;
  background: var(--sideMenuColor);
  width: 100%;
  height: 100%;
  border-radius: 10px;
  grid-area: side2;
}

.menu-library-title {
  display: flex;
  align-items: center;
  gap: 15px;
  padding: 10px;
  font-size: 0.95rem;
  color: var(--fontColorSmall);
  transition: 500ms;
}

.menu-library-title:hover {
    transform: scale(1.05);
    color: var(--fontColorTitle)
  }


.menu-library-items button {
  display: flex;
  flex-direction: column;
  padding: 10px;
  font-size: .85rem;
  font-weight: 600;
  color: var(--fontColorSmall);
  background: none;
  border: none;
  cursor: pointer;
  transition: 500ms;
}

.menu-library-items button:hover {
  color: var(--fontColorTitle)
}

</style>