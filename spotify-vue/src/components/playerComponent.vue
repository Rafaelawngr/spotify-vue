<script>

export default {
  name: 'playerComponent',

  setup() {
   
    

    return {
      nowPlaying: [
        {
          imgSrc: 'https://i.scdn.co/image/ab67616d0000b2739478c87599550dd73bfa7e02',
          musicName: 'teste',
          artistName: 'teste'
        },
      ]
    }
  }
}

</script>

<template>
  <body>
  <div v-for="song in nowPlaying" class="player-music">
      <img class="picture"
           :src="song.imgSrc" alt=""/>
    <div  class="music">
      <h1>{{ song.musicName }}</h1>
      <h2>{{ song.artistName }}</h2>
    </div>
    <div class="like-music">
      <span class="material-symbols-outlined" @click="hearted">favorite</span>
      <span class="material-symbols-outlined">branding_watermark</span>
    </div>
  </div>
  <div class="now-playing">
    <div class="player-controls">
      <span class="material-symbols-outlined small">shuffle</span>
      <span class="material-symbols-outlined medium">skip_previous</span>
      <span class="material-symbols-outlined large">play_circle</span>
      <span class="material-symbols-outlined medium">skip_next</span>
      <span class="material-symbols-outlined small">repeat</span>
    </div>

    <div class="progress-bar">
      <div class="bar">
        <progress value="0" max="1"></progress>
      </div>
      <div class="point"></div>
      <div class="time">
        <p class="current-time">0:00</p>
        <p class="duration">3:40</p>
      </div>
    </div>
  </div>

  <div class="player-infos">
    <span class="material-symbols-outlined">slideshow</span>
    <span class="material-symbols-outlined">mic_external_on</span>
    <span class="material-symbols-outlined">menu</span>
    <span class="material-symbols-outlined">speaker</span>
    <div class="volume">
      <span class="material-symbols-outlined smaller">volume_down</span>
      <progress class="volume" value="0" max="1"></progress>
      <div class="point2"></div>
    </div>
    <span class="material-symbols-outlined">open_in_full</span>
  </div>
  </body>
</template>


<style scoped>
body {
  justify-content: space-between;
  display: flex;
  align-items: center;
  width: 100%;
  height: 100%;
  grid-area: footer;
}

.player-music {
  display: flex;
  gap: 25px;
  margin-left: 15px;
  align-items: center;
}

.picture {
  width: 60px;
  height: 60px;
  background-color: #404040;
  border-radius: 50%;
  border: none;
}

.music {
  display: flex;
  flex-direction: column;
  gap: 5px;
  color: var(--fontColorTitle);
}

h1 {
  font-size: 1.1rem;
  font-weight: 500;
}

h2 {
  font-size: .9rem;
  font-weight: 300;
}

.like-music {
  display: flex;
  gap: 15px;
}

.now-playing {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.player-controls {
  padding: 15px;
  display: flex;
  align-items: center;
  gap: 20px
}

.material-symbols-outlined {
  font-variation-settings: 'FILL' 0,
  'wght' 300,
  'GRAD' 0,
  'opsz' 20;
  color: var(--fontColorSmall);
  font-size: 22px;
  transition: 500ms;
}

.large {
  font-variation-settings: 'FILL' 1;
  font-size: 48px;
}

.medium {
  font-variation-settings: 'FILL' 1;
  font-size: 36px;
}

.small {
  font-size: 22px;
}

.smaller {
  font-size: 28px;
}

.material-symbols-outlined:hover {
  color: var(--fontColorTitle);
}

.player-infos {
  margin-right: 15px;
  display: flex;
  align-items: center;
  gap: 10px;
}

.now-playing {
  width: 10%;
}

.progress-bar {
  height: 8px;
  border-radius: 5px;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  border: 1px solid var(--sideMenuColor);
}

.bar {
  width: 100%;
  height: 6px;
  display: flex;
  background-color: var(--sideMenuColor);
}

progress {
  width: 380px;
  height: 6px;
  cursor: pointer;
}

.point {
  width: 15px;
  height: 15px;
  background-color: var(--fontColorTitle);
  border-radius: 50%;
  margin-left: -2px;
}

.time {
  display: flex;
  justify-content: space-between;
  color: var(--fontColorSmall);
  font-size: .8rem;
  width: 120%;
  position: absolute;
}

.volume {
  display: flex;
  align-items: center;
  width: 120px;
  height: 6px;
  cursor: pointer;
}

.point2 {
  width: 14px;
  height: 10px;
  background-color: var(--fontColorTitle);
  border-radius: 50%;
  margin-left: -2px;
}
</style>

