<template>
  <div
    class="flex flex-col flex-wrap max-w-md rounded bg-black bg-opacity-75 px-2 py-2 items-center tracking-widest divide-y"
  >
    <div class="px-2 py-2">
      <div class="font-bold text-2xl mb-2 text-white uppercase">{{ rover.name }}</div>
    </div>
    <div class="px-2 py-2 inline-flex divide-x">
      <p class="text-white px-2 text-lg">Launch Date: {{ rover.launch_date }}</p>
      <p class="text-white px-2 text-lg">Landing Date: {{ rover.landing_date }}</p>
    </div>
    <div v-if="rover.status === 'active'">
      <div class="text-lg text-green-500 capitalize">
        <span class="text-lg px-2 text-white">Status:</span>
        {{ rover.status }}
      </div>
    </div>
    <div v-else>
      <div class="text-lg text-red-500 capitalize">
        <span class="text-lg px-2 text-white">Status:</span>
        {{ rover.status }}
      </div>
    </div>
    <div class="inline-flex py-2 divide-x">
      <div class="text-lg px-2 text-white">Max Marsian Sol: {{ rover.max_sol }}</div>
      <div class="text-lg px-2 text-white">Max Earth Date: {{ rover.max_date }}</div>
    </div>
    <div class="text-lg px-2 text-white">Total Photos: {{ rover.total_photos }}</div>
    <div class="flex flex-col py-2 items-center divide-y">
      <div class="text-lg text-white">Cameras</div>
      <div
        class="text-base text-white tracking-widest leading-snug py-1"
        v-bind:key="i"
        v-for="(camera, i) in rover.cameras"
      >{{ camera.name }} | {{ camera.full_name }}</div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'Curiosity',
  data() {
    return {
      rover: {},
    }
  },
  async created() {
    try {
      const res = await axios.get(
        'https://mars-photos.herokuapp.com/api/v1/rovers/Curiosity/'
      )

      this.rover = res.data.rover
    } catch (err) {
      console.log(err)
    }
  },
}
</script>

<style>
</style>