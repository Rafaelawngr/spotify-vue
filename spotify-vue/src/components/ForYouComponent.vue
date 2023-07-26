<script>

export default {
  name: 'ForYouComponent',
  props: {
    titulo: String,
  },

  setup() {

    return {
      albums: [
        {
          imgSrc: 'https://media.npr.org/assets/img/2012/12/03/mellon-collie-and-the-infinite-sadness---cover-art_custom-ab1a9effa9ca9ee17ff640cdda0fc03fc5d09712.jpg',
          albumName: 'Mellon Collie And The Infinite Sadness',
          artistName: 'The Smashing Pumpkins'
        },

        {
          imgSrc: 'https://m.media-amazon.com/images/I/91UUbDedB1S._UF1000,1000_QL80_.jpg',
          albumName: 'Happier Than Ever',
          artistName: 'Billie Eilish'
        },

        {
          imgSrc: 'https://akamai.sscdn.co/uploadfile/letras/albuns/5/2/9/0/01647262484.jpg',
          albumName: 'Gêmeos',
          artistName: 'Terno Rei'
        },

        {
          imgSrc: 'https://m.media-amazon.com/images/I/91N5ovoYjoL._UF1000,1000_QL80_.jpg',
          albumName: 'Brand New Eyes',
          artistName: 'Paramore'
        },

        {
          imgSrc: 'https://upload.wikimedia.org/wikipedia/pt/thumb/d/dc/The_Black_Parade.jpg/220px-The_Black_Parade.jpg',
          albumName: 'The Black Parade',
          artistName: 'My Chemical Romance'
        },

        {
          imgSrc: 'https://i.scdn.co/image/ab67616d0000b2739478c87599550dd73bfa7e02',
          albumName: "Hollywood's Bleeding",
          artistName: 'Post Malone'
        },
      ]
    }
  },

}

</script>

<template>
  <h1>Tocados recentemente</h1>
  <div class="all-shows">
    <div v-for="(album, index) in albums" :key="index" class="playlist">
      <img :src="album.imgSrc" :alt="'Capa do álbum ' + album.albumName">
      <h2>{{ album.albumName }}</h2>
      <h3>{{ album.artistName }}</h3>
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