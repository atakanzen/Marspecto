<template>
  <div v-if="this.loading"></div>
  <div v-else>
    <div
      class="flex flex-col max-w-lg rounded bg-black bg-opacity-75 px-3 py-3 items-center tracking-widest leading-tight select-none"
    >
      <div class="px-2 py-2">
        <div class="font-bold text-2xl mb-2 text-white uppercase">{{ rover.name }}</div>
      </div>
      <div class="px-2 py-2 inline-flex divide-x border">
        <p class="text-white px-2 text-lg">Launch Date: {{ rover.launch_date }}</p>
        <p class="text-white px-2 text-lg">Landing Date: {{ rover.landing_date }}</p>
      </div>
      <div v-if="rover.status === 'active'">
        <div class="text-lg text-green-500 capitalize border border-t-0 border-b-0 p-2">
          <span class="text-lg px-2 text-white">Status:</span>
          {{ rover.status }}
        </div>
      </div>
      <div v-else>
        <div class="text-lg text-red-500 capitalize border border-t-0 border-b-0 p-2">
          <span class="text-lg px-2 text-white">Status:</span>
          {{ rover.status }}
        </div>
      </div>
      <div class="inline-flex py-2 divide-x border">
        <div class="text-lg px-2 text-white">Max Marsian Sol: {{ rover.max_sol }}</div>
        <div class="text-lg px-2 text-white">Max Earth Date: {{ rover.max_date }}</div>
      </div>
      <div
        class="text-lg p-3 border border-t-0 border-b-0 text-white"
      >Total Photos: {{ rover.total_photos }}</div>
      <div class="flex flex-col p-3 items-center divide-y border">
        <div class="text-lg text-white">Cameras</div>
        <div
          class="text-base text-white tracking-widest leading-snug py-1"
          v-bind:key="i"
          v-for="(camera, i) in rover.cameras"
        >{{ camera.name }} | {{ camera.full_name }}</div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'Opportunity',
  data() {
    return {
      rover: {},
      loading: true,
    }
  },
  async created() {
    try {
      const res = await axios.get(
        'https://mars-photos.herokuapp.com/api/v1/rovers/Opportunity/'
      )

      this.rover = res.data.rover
      this.loading = false
    } catch (err) {
      console.log(err)
    }
  },
}
</script>

<style>
</style>