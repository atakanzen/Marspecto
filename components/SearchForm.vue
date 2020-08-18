<template>
  <div>
    <div v-if="this.photos.length === 0">
      <div class="flex flex-col w-screen items-center">
        <form v-on:submit.prevent="getPhotos" class="search-form lg:w-1/2 w-screen space-y-2">
          <label for="rover" class="form-label">Rover</label>
          <select
            name="rover"
            id="rover"
            class="rover-select w-1/2 focus:outline-none focus:border-orange-500 lg:appearance-none"
            v-model="rover"
          >
            <option value="curiosity">Curiosity</option>
            <option value="opportunity">Opportunity</option>
            <option value="spirit">Spirit</option>
          </select>
          <label for="sol" class="form-label">Sol</label>
          <span
            class="text-orange-400 text-sm text-opacity-75 font-light"
          >You can check Rovers page for the latest Sol</span>
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
    <div v-else class="flex flex-col space-y-2 static overflow-auto h-screen">
      <Photos :photos="this.currentPhotos" :loading="this.loading" class="mt-2" />
      <Pagination
        :photosPerPage="this.photosPerPage"
        :totalPhotos="this.photos.length"
        :paginate="this.paginate"
        :getPhotos="this.getCurrentPhotos"
      />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import Photos from "./Photos";
import Pagination from "./Pagination";

export default {
  name: "SearchForm",
  components: {
    Photos,
    Pagination,
  },
  data() {
    return {
      rover: "",
      sol: "",
      loading: true,
      photos: [],
      currentPhotos: [],
      currentPage: 1,
      photosPerPage: 25,
    };
  },
  methods: {
    async getPhotos() {
      try {
        this.loading = true;
        const res = await axios.get(
          `https://mars-photos.herokuapp.com/api/v1/rovers/${this.rover}/photos?sol=${this.sol}`
        );
        this.photos = res.data.photos;
        this.loading = false;
        this.getCurrentPhotos();
      } catch (err) {
        console.log(err);
      }
    },
    getCurrentPhotos() {
      const lastIndex = this.currentPage * this.photosPerPage;
      const firstIndex = lastIndex - this.photosPerPage;
      this.currentPhotos = this.photos.slice(firstIndex, lastIndex);
    },
    paginate(number) {
      this.currentPage = number;
    },
  },
};
</script>

<style scoped>
.search-form {
  @apply bg-black bg-opacity-75 p-6 m-6 flex flex-col items-center justify-center;
}

.form-label {
  @apply tracking-widest text-xl text-orange-700 text-center;
}

.rover-select {
  @apply text-center tracking-widest font-light;
}

.sol-input {
  @apply appearance-none border rounded-sm text-center;
}

.btn {
  @apply block bg-orange-700 bg-opacity-75 rounded-sm text-white text-xl font-hairline;
}
</style>
