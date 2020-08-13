<template>
  <div class="flex justify-center items-center h-screen">
    <form v-on:submit="getPhotos" class="form lg:w-1/2 w-screen space-y-4">
      <label for="rover" class="label">Rover</label>
      <select
        name="rover"
        id="rover"
        class="select-rover w-1/2 focus:outline-none focus:border-orange-500"
        v-model="rover"
      >
        <option value="curiosity">Curiosity</option>
        <option value="opportunity">Opportunity</option>
        <option value="spirit">Spirit</option>
      </select>
      <label for="sol" class="label">Sol</label>
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
</template>

<script>
import axios from 'axios'

export default {
  head() {
    return {
      title: 'Marspecto | Search',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: "Search photos that's been taken on Mars by NASA rovers",
        },
      ],
    }
  },
  data() {
    return {
      rover: '',
      sol: '',
    }
  },
  methods: {
    getPhotos() {
      console.log(123)
    },
  },
}
</script>

<style scoped>
.form {
  @apply bg-black bg-opacity-75  p-6 m-6  flex flex-col items-center justify-center;
}

.label {
  @apply tracking-widest text-xl text-orange-700 text-center;
}

.select-rover {
  @apply appearance-none text-center tracking-widest font-light;
}

.sol-input {
  @apply appearance-none border rounded-sm text-center;
}

.btn {
  @apply block bg-orange-700 bg-opacity-75  rounded-sm text-white text-xl font-hairline;
}
</style>