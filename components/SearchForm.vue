<template>
  <div>
    <div class="flex flex-col w-screen items-center">
      <form v-on:submit.prevent="getPhotos" class="search-form lg:w-1/2 w-screen space-y-4">
        <label for="rover" class="form-label">Rover</label>
        <select
          name="rover"
          id="rover"
          class="rover-select w-1/2 focus:outline-none focus:border-orange-500"
          v-model="rover"
        >
          <option value="curiosity">Curiosity</option>
          <option value="opportunity">Opportunity</option>
          <option value="spirit">Spirit</option>
        </select>
        <label for="sol" class="form-label">Sol</label>
        <input
          type="text"
          id="sol"
          class="sol-input placeholder-gray-900 focus:outline-none focus:border-orange-700 w-1/2"
          placeholder="Mars Sol"
          v-model="sol"
        />
        <button type="submit" class="btn w-1/2">Search</button>
      </form>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'SearchForm',
  data() {
    return {
      rover: '',
      sol: '',
      loading: false,
      photos: [],
      currentPage: 1,
      photosPerPage: 25,
    }
  },
  methods: {
    async getPhotos() {
      try {
        this.loading = true
        const res = await axios.get(
          `https://mars-photos.herokuapp.com/api/v1/rovers/${this.rover}/photos?sol=${this.sol}`
        )
        console.log(this.currentPage)

        this.photos = res.data
        this.loading = false
      } catch (err) {
        console.log(err)
      }
    },
    getCurrentPhotos() {
      // Getting current photos
      const lastIndex = this.currentPage * this.photosPerPage
      const firstIndex = lastIndex - this.photosPerPage
      const currentPhotos = this.photos.slice(firstIndex, lastIndex)
      console.log(lastIndex)
      console.log(firstIndex)
      console.log(currentPhotos)
    },
  },
}
</script>

<style scoped>
.search-form {
  @apply bg-black bg-opacity-75 p-6 m-6 flex flex-col items-center justify-center;
}

.form-label {
  @apply tracking-widest text-xl text-orange-700 text-center;
}

.rover-select {
  @apply appearance-none text-center tracking-widest font-light;
}

.sol-input {
  @apply appearance-none border rounded-sm text-center;
}

.btn {
  @apply block bg-orange-700 bg-opacity-75 rounded-sm text-white text-xl font-hairline;
}
</style>
