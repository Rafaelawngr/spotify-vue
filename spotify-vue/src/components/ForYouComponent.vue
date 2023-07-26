<script setup>

</script>

<template>
  <h1>Seus programas</h1>
  <div class="all-shows">
    <div class="playlist">
      <img src="https://t3.ftcdn.net/jpg/02/68/55/60/360_F_268556012_c1WBaKFN5rjRxR2eyV33znK4qnYeKZjm.jpg">
      <h2>Nome do programa</h2>
      <h3>Nome do artista</h3>
    </div>
    
    <!--  componentes repetidos -->
    <div class="playlist">
      <img src="https://t3.ftcdn.net/jpg/02/68/55/60/360_F_268556012_c1WBaKFN5rjRxR2eyV33znK4qnYeKZjm.jpg">
      <h2>Nome do programa</h2>
      <h3>Nome do artista</h3>
    </div>
    <div class="playlist">
      <img src="https://t3.ftcdn.net/jpg/02/68/55/60/360_F_268556012_c1WBaKFN5rjRxR2eyV33znK4qnYeKZjm.jpg">
      <h2>Nome do programa</h2>
      <h3>Nome do artista</h3>
    </div>
    <div class="playlist">
      <img src="https://t3.ftcdn.net/jpg/02/68/55/60/360_F_268556012_c1WBaKFN5rjRxR2eyV33znK4qnYeKZjm.jpg">
      <h2>Nome do programa</h2>
      <h3>Nome do artista</h3>
    </div>
    <div class="playlist">
      <img src="https://t3.ftcdn.net/jpg/02/68/55/60/360_F_268556012_c1WBaKFN5rjRxR2eyV33znK4qnYeKZjm.jpg">
      <h2>Nome do programa</h2>
      <h3>Nome do artista</h3>
    </div>
    <div class="playlist">
      <img src="https://t3.ftcdn.net/jpg/02/68/55/60/360_F_268556012_c1WBaKFN5rjRxR2eyV33znK4qnYeKZjm.jpg">
      <h2>Nome do programa</h2>
      <h3>Nome do artista</h3>
    </div>
  </div>
</template>

<style scoped>
h1 {
  margin-top: 10px;
  color: var(--fontColorTitle);
  padding: 10px;
  font-size: 1.15rem;
}

.all-shows {
  display: flex;
  padding: 10px;
  gap: 20px;
}

.playlist {
  display: flex;
  flex-direction: column;
  padding: 20px;
  width: 180px;
  height: 280px;
  border-radius: 5px;
  background: rgba(49, 49, 49, 0.53);
  gap: 10px;
}

.playlist img {
  width: 100%;
  border-radius: 3px;
}


h2 {
  font-size: .95rem;
  color: var(--fontColorTitle);
}

h3 {
  font-size: .85rem;
  font-weight: 400;
  color: var(--fontColorSmall);
}

</style>