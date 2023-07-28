<script>

import { ref, watchEffect } from "vue";

export default {
  name: 'playerComponent',

  props: {
    selectedSong: Object,
  },

  setup(props) {
    const isLiked = ref(false);
    const toggleLike = () => {
      isLiked.value = !isLiked.value;
    };

    const isPlaying = ref(false);
    const currentSong = ref(props.selectedSong);
    
    watchEffect(() => {
      currentSong.value = props.selectedSong;
    })
    
    const togglePlayPause = () => {
      isPlaying.vlaue = !isPlaying.value
    }
    
    return {
      isLiked,
      toggleLike,
      isPlaying,
      togglePlayPause,
      
      currentSong: {
          imgSrc: 'https://akamai.sscdn.co/uploadfile/letras/albuns/5/2/9/0/01647262484.jpg',
          musicName: 'Dias da Juventude',
          artistName: 'Terno Rei',
          duration: '3:12'
        },
    }
}
};

</script>

<template>
  <body>
  <div v-if="currentSong" class="player-music">
      <img class="picture"
           :src="currentSong.imgSrc" alt=""/>
    <div  class="music">
      <h1>{{ currentSong.musicName }}</h1>
      <h2>{{ currentSong.artistName }}</h2>
    </div>
    <div class="like-music">
      <span class="material-symbols-outlined" :class="{ clicked: isLiked }"
            @click="toggleLike">favorite</span>
      <span class="material-symbols-outlined">branding_watermark</span>
    </div>
  </div>
  <div class="now-playing">
    <div class="player-controls"  >
      <span class="material-symbols-outlined small">shuffle</span>
      <span class="material-symbols-outlined medium">skip_previous</span>
      <span class="material-symbols-outlined large" :class="{ clicked: isPlaying }" @click="togglePlayPause"> {{ isPlaying ? 'pause-cirlce' : 'play_circle' }}</span>
      <span class="material-symbols-outlined medium">skip_next</span>
      <span class="material-symbols-outlined small">repeat</span>
    </div>

    <div class="progress-bar">
      <div class="bar">
        <progress value="0" max="1"></progress>
      </div>
      <div class="point"></div>
      <div class="time" v-if="currentSong">
        <p class="current-time">0:00</p>
        <p class="duration">{{  currentSong.duration }}</p>
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
      <input class="slider" type="range" min="0" max="100" >
    </div>
    <span class="material-symbols-outlined">open_in_full</span>
  </div>
  </body>
</template>


<style scoped>
body {
  position: sticky;
  bottom: 0;
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
  cursor: pointer;
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
  gap: 20px;
}

.material-symbols-outlined {
  font-variation-settings: 'FILL' 0,
  'wght' 300,
  'GRAD' 0,
  'opsz' 20;
  color: var(--fontColorSmall);
  font-size: 22px;
  transition: 500ms;
  cursor: pointer;
}

.clicked {
  font-variation-settings: 'FILL' 1
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
  transform: scale(1.05);
}

.player-infos {
  margin-right: 15px;
  display: flex;
  align-items: center;
  gap: 10px;
}

.progress-bar {
  height: 8px;
  border-radius: 5px;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
}


.bar {
  width: 100%;
  height: 5px;
  display: flex;
  cursor: pointer;
  border-radius: 5px;
  background-color: var(--sideMenuColor);

}

progress {
  width: 500px;
  height: 5px;
  background: var(--sideMenuColor);
  border-radius: 5px;
}

.point {
  width: 15px;
  height: 15px;
  background-color: var(--fontColorSmall);
  border-radius: 50%;
  margin-left: -2px;
}

.time {
  display: flex;
  justify-content: space-between;
  color: var(--fontColorSmall);
  font-size: .8rem;
  width: 115%;
  position: absolute;
}

.volume {
  display: flex;
  align-items: center;
  justify-content: center;
}

.slider {
  -webkit-appearance: none;
  -webkit-transition: 200ms;
  width: 100%;
  height: 5px;
  background-color: var(--sideMenuColor);
  border-radius: 5px;
  transition: 500ms;
}

.slider::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 12px;
  height: 12px;
  background: var(--fontColorSmall);
  border-radius: 50%;
  cursor: pointer;
}


</style>

