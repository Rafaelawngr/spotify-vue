<script>

import { onMounted, ref, watch} from "vue";
import {TYPES} from "../assets/utils";


export default {
  name: 'ForYouComponent',
  props: {
    titulo: String,
    type: Number,
    reset: Boolean,
    selectedSong: Object
  },
  emits: [
    "show-all"
  ],

  setup(props, {emit}) {
    
    const selectedSong = ref (Number)
    
    const showSelectedSong = (song) => {
      selectedSong.value = song;
    }

    const selectedList = ref([])

    let albumsRecommended = [
      {
        imgSrc: 'https://media.npr.org/assets/img/2012/12/03/mellon-collie-and-the-infinite-sadness---cover-art_custom-ab1a9effa9ca9ee17ff640cdda0fc03fc5d09712.jpg',
        albumName: 'Mellon Collie And The Infinite Sadness',
        artistName: 'The Smashing Pumpkins',
        duration: '4:53'
      },

      {
        imgSrc: 'https://m.media-amazon.com/images/I/91UUbDedB1S._UF1000,1000_QL80_.jpg',
        albumName: 'Happier Than Ever',
        artistName: 'Billie Eilish',
        duration: '2:58'
      },

      {
        imgSrc: 'https://akamai.sscdn.co/uploadfile/letras/albuns/5/2/9/0/01647262484.jpg',
        albumName: 'Gêmeos',
        artistName: 'Terno Rei',
        duration: '3:25'
      },

      {
        imgSrc: 'https://m.media-amazon.com/images/I/91N5ovoYjoL._UF1000,1000_QL80_.jpg',
        albumName: 'Brand New Eyes',
        artistName: 'Paramore',
        duration: '4:12'
      },

      {
        imgSrc: 'https://upload.wikimedia.org/wikipedia/pt/thumb/d/dc/The_Black_Parade.jpg/220px-The_Black_Parade.jpg',
        albumName: 'The Black Parade',
        artistName: 'My Chemical Romance',
        duration: '5:11'
      },

      {
        imgSrc: 'https://i.scdn.co/image/ab67616d0000b2739478c87599550dd73bfa7e02',
        albumName: "Hollywood's Bleeding",
        artistName: 'Post Malone',
        duration: '2.38'
      },
      {
        imgSrc: 'https://akamai.sscdn.co/uploadfile/letras/albuns/4/1/9/7/721091556657074.jpg',
        albumName: "<atrás/além>",
        artistName: 'O Terno',
        duration: '3:22'
      },
      {
        imgSrc: 'https://m.media-amazon.com/images/I/81pf4NjVhfL._UF1000,1000_QL80_.jpg',
        albumName: 'BALLADS1',
        artistName: 'Joji'
      },

      {
        imgSrc: 'https://akamai.sscdn.co/uploadfile/letras/albuns/0/b/7/8/600411507913353.jpg',
        albumName: 'Cuscobayo',
        artistName: 'Cuscobayo'
      },

      {
        imgSrc: 'https://upload.wikimedia.org/wikipedia/pt/5/51/CTE_Melophobia.jpg',
        albumName: 'Melophobia',
        artistName: 'Cage The Elephant'
      },

      {
        imgSrc: 'https://m.media-amazon.com/images/I/A1p1y56msuL._UF1000,1000_QL80_.jpg',
        albumName: 'The Album',
        artistName: 'Jonas Brothers'
      },

    ]

    let albumsHits = [
      {
        imgSrc: 'https://i.scdn.co/image/ab67706f000000025a17b6b5ca62479fe6eb1076',
        albumName: 'Top Brasil',
        artistName: 'Vulgo FK e os maiores hits do país'
      },

      {
        imgSrc: 'https://wesleysafadao.com.br/ws/wp-content/uploads/2021/01/whatsapp-image-2021-01-15-at-18-51-31.jpeg',
        albumName: 'Esquenta Sertanejo',
        artistName: 'O melhor do sertanejo em uma só playlist!'
      },

      {
        imgSrc: 'https://images.genius.com/9981be1fb5fa67fb8ba50d3f54b7b73e.640x640x1.jpg',
        albumName: "Today's Top Hits",
        artistName: 'Travis Scott is on top of the Hottest 50!'
      },

      {
        imgSrc: 'https://i.scdn.co/image/ab67706f00000002cba280fdd19d553842ccbee1',
        albumName: 'Hot Hits Brasil',
        artistName: 'Os grandes hits do momento estão aqui!'
      },

      {
        imgSrc: 'https://i.scdn.co/image/ab67706f00000002d971c6c23114fc7636dc23eb',
        albumName: 'Viral Hits',
        artistName: 'Viral, trending and taking off.'
      },
    ]

    let albumsPodcasts = [
      {
        imgSrc: 'https://cdns-images.dzcdn.net/images/talk/1092be16f0b601fb78cf309e56d83446/264x264.jpg',
        albumName: 'Quinta Misteriosa',
        artistName: 'Jaqueline Guerreiro'
      },

      {
        imgSrc: 'https://i.scdn.co/image/ab6765630000ba8a41e6fdb39dd6cbda1db0f609',
        albumName: 'Papo de UX',
        artistName: 'Luan Mateus'
      },

      {
        imgSrc: 'https://i1.sndcdn.com/avatars-drypf0vYvBrzTHDy-s2i0hw-t500x500.jpg',
        albumName: 'Não Inviabilize',
        artistName: 'Déia Freitas'
      },

      {
        imgSrc: 'https://i.scdn.co/image/ab67656300005f1f386f458ac9f4254e421eb4b0',
        albumName: 'Psicologia na Prática',
        artistName: 'Alana Anijar'
      },

      {
        imgSrc: 'https://m.media-amazon.com/images/I/51FH-7VPPlL.jpg',
        albumName: 'A Silenciosa',
        artistName: 'Chico Felitti'
      },

      {
        imgSrc: 'https://s2.glbimg.com/77Crj-wzU6aTIxRwTt-hdo2kiVY=/600x600/smart/https://s3.glbimg.com/v1/AUTH_c3c606ff68e7478091d1ca496f9c5625/audiopub-podcasts/bs/2022/D/H/Gg3iiASvmYXiIoi7O62w/capa-modus-operandi-1000x1000.png',
        albumName: 'Modus Operandi',
        artistName: 'Globoplay'
      },
    ]

    onMounted(() => {
      if (props.type === TYPES.RECOMMENDED) {
        selectedList.value = albumsRecommended.slice(0, 7)

      } else if (props.type === TYPES.HITS) {
        selectedList.value = albumsHits
      } else {
        selectedList.value = albumsPodcasts
      }
    })

    watch(() => props.reset, () => {
      if (props.reset === true) {
        selectedList.value = albumsRecommended.slice(0, 7)
      }
    })
    const showAll = () => {
      selectedList.value = albumsRecommended
      emit("show-all")
    }
    return {
      showAll,
      selectedList,
      selectedSong,
      showSelectedSong
    }
  },
}

</script>

<template>
  <div class="title">
    <h1>{{ titulo }}</h1>
    <button class="show-more" @click="showAll">Mostrar tudo</button>
  </div>
  <div class="all-shows">
    <div v-for="(album, index) in selectedList" :key="index" class="playlist">
      <img :src="album.imgSrc" :alt="'Capa do álbum ' + album.albumName">
      <h2>{{ album.albumName }}</h2>
      <h3>{{ album.artistName }}</h3>
      <button class="play-music" v-for="song in selectedList" :key="song.albumName"  @click="showSelectedSong"> <span class="material-symbols-outlined">
play_arrow
</span></button>
    </div>
  </div>
</template>

<style scoped>

.title {
  display: flex;
  justify-content: space-between;
  padding: 10px 20px;
  align-items: center;
}

h1 {
  margin-top: 10px;
  color: var(--fontColorTitle);
  font-size: 1.15rem;
}

.show-more {
  font-size: .85rem;
  font-weight: 500;
  color: var(--fontColorSmall);
  transition: 500ms;
  cursor: pointer;
  background: none;
  border: none;
}

.show-more:hover {
  color: var(--fontColorTitle);
}

.all-shows {
  margin-bottom: 20px;
  display: flex;
  flex-wrap: wrap;
  padding: 20px;
  gap: 20px;
}

.playlist {
  display: flex;
  flex-direction: column;
  padding: 20px;
  width: 200px;
  height: 300px;
  border-radius: 5px;
  background: #1f1f1f;
  gap: 10px;
  cursor: pointer;
  transition: 500ms;
  position: relative;
  box-shadow: 5px 5px 7px 0 rgba(16, 16, 16, 0.20);
}

.playlist:hover {
  background: #282828;
}

.playlist:hover .play-music {
  opacity: 1;
}

.playlist img {
  width: 100%;
  border-radius: 3px;
  box-shadow: 5px 5px 10px 0 rgba(16, 16, 16, 0.40);
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

.play-music {
  display: flex;
  opacity: 0;
  align-items: center;
  justify-content: center;
  padding: 5px;
  border: none;
  box-shadow: 4px 4px 8px 0 rgba(16, 16, 16, 0.10);
  position: absolute;
  bottom: 130px;
  right: 30px;
  cursor: pointer;
  background: #1ED760;
  border-radius: 50%;
  transition: 500ms;
}

.play-music:hover {
  transform: scale(1.1);
}

.material-symbols-outlined {
  font-variation-settings: 'FILL' 1;
  color: #000;
  font-size: 30px;
}


</style>