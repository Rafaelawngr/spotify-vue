<script setup>

</script>

<template>
  <h1>Bom dia</h1>
  <div class="all-playlists">
  <div class="playlist">
    <img src="https://t3.ftcdn.net/jpg/02/68/55/60/360_F_268556012_c1WBaKFN5rjRxR2eyV33znK4qnYeKZjm.jpg" >
  <h2>Nome da playlist</h2>
  </div>
<!--  componentes repetidos -->
    <div class="playlist">
      <img src="https://t3.ftcdn.net/jpg/02/68/55/60/360_F_268556012_c1WBaKFN5rjRxR2eyV33znK4qnYeKZjm.jpg" >
      <h2>Nome da playlist</h2>
    </div>
    <div class="playlist">
      <img src="https://t3.ftcdn.net/jpg/02/68/55/60/360_F_268556012_c1WBaKFN5rjRxR2eyV33znK4qnYeKZjm.jpg" >
      <h2>Nome da playlist</h2>
    </div>
    <div class="playlist">
      <img src="https://t3.ftcdn.net/jpg/02/68/55/60/360_F_268556012_c1WBaKFN5rjRxR2eyV33znK4qnYeKZjm.jpg" >
      <h2>Nome da playlist</h2>
    </div>
    <div class="playlist">
      <img src="https://t3.ftcdn.net/jpg/02/68/55/60/360_F_268556012_c1WBaKFN5rjRxR2eyV33znK4qnYeKZjm.jpg" >
      <h2>Nome da playlist</h2>
    </div>
    <div class="playlist">
      <img src="https://t3.ftcdn.net/jpg/02/68/55/60/360_F_268556012_c1WBaKFN5rjRxR2eyV33znK4qnYeKZjm.jpg" >
      <h2>Nome da playlist</h2>
    </div>
  </div>
</template>

<style scoped>

.all-playlists {
  display: grid;
  padding: 10px;
  gap: 10px;
  grid-template-columns: 1fr 1fr 1fr;
  grid-template-rows: 1fr 1fr;
}

  .playlist {
    display: flex;
    align-items: center;
    width: 100%;
    height: 100%;
    border-radius: 5px;
    background: rgba(86, 86, 86, 0.49);
    gap: 10px;
  }

  .playlist img {
    width: 80px;
    height: 80px;
    border-radius: 5px 0 0 5px ;
  }

h1 {
  margin-top: 10px;
  color: var(--fontColorTitle);
  padding: 10px;
  font-size: 1.5rem;
}
  
  h2 {
    font-size: .95rem;
    color: var(--fontColorTitle);
  }
</style>