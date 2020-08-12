<template>
  <div class="flex justify-center items-center h-screen">
    <form
      class="bg-black bg-opacity-75 w-screen lg:w-1/2 p-6 m-6 space-y-4 flex flex-col items-center justify-center"
    >
      <label for="rover" class="tracking-widest text-xl text-orange-700 text-center">Rover</label>
      <select
        name="rover"
        id="rover"
        class="appearance-none text-center tracking-widest font-light w-1/2 focus:outline-none focus:border-orange-500"
        v-model="rover"
      >
        <option value="curiosity">Curiosity</option>
        <option value="opportunity">Opportunity</option>
        <option value="spirit">Spirit</option>
      </select>
      <label for="sol" class="tracking-widest text-orange-700 text-center text-xl">Sol</label>
      <input
        type="text"
        id="sol"
        class="appearance-none border rounded-sm text-center focus:outline-none focus:border-orange-700 w-1/2"
        placeholder="Mars Sol"
        v-model="sol"
      />
      <button
        type="submit"
        class="block bg-orange-700 bg-opacity-75 w-1/2 rounded-sm text-white text-xl font-hairline"
        v-on:click="getPhotos"
      >Search</button>
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

<style>
</style>