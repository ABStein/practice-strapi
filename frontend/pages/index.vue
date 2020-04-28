<template>
  <div>
    <div class="navbar bg-gray-300">
      <Navbar/>
    </div>
    <div class="title">
      <h1>My Favorite Albums</h1>
    </div>
    <div class="container items-center">
      <div v-for="album in albumsList" v-bind:key="album" class="max-w-sm rounded shadow-md m-2">
        <img class="" :src="'http://localhost:1337/' + album.image.url" alt="">
        <div class="px-6 py-4">
          <div class="font-bold text-xl mb-2">
            {{ album.name }}
          </div>
          <p class="text-gray-700 text-base">
            Description: {{ album.description }}
          </p>
        </div>
        <p class="text-gray-700 text-base">
          Genre: {{ album.genres[0].name }}
        </p>
      </div>
    </div>
  </div>
</template>

<script>
import albumsQuery from '~/apollo/queries/album/albums.gql'

const Navbar = () => import('~/components/Navbar.vue')

export default {
  components: {
    Navbar
  },
  data () {
    return {
      albums: [],
      query: ''
    }
  },
  apollo: {
    albums: {
      prefetch: true,
      query: albumsQuery
    }
  },
  computed: {
    albumsList () {
      return this.albums.filter((album) => {
        return album.name.toLowerCase().includes(this.query.toLowerCase())
      })
    }
  }
}

</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
  @apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
.container {
  margin: auto auto;
  padding: 10px;
  min-height: 20vh;
  display: flex;
  /* flex-direction: column; */
  justify-content: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-weight: 300;
  text-align: center;
  font-size: 50px;
  color: #35495e;
  letter-spacing: 1px;
}
</style>
