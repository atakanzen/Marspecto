<template>
  <div v-if="this.loading"></div>
  <div v-else>
    <div class="card">
      <div class="px-2 py-2">
        <div class="name">{{ rover.name }}</div>
      </div>
      <div class="launch-dates divide-x">
        <p class="launch-date">Launch Date: {{ rover.launch_date }}</p>
        <p class="launch-date">Landing Date: {{ rover.landing_date }}</p>
      </div>
      <div v-if="rover.status === 'active'">
        <div class="status">
          <span class="text-white">Status:</span>
          {{ rover.status }}
        </div>
      </div>
      <div v-else>
        <div class="status">
          <span class="text-white">Status:</span>
          {{ rover.status }}
        </div>
      </div>
      <div class="max-dates divide-x">
        <div class="max-date">Max Marsian Sol: {{ rover.max_sol }}</div>
        <div class="max-date">Max Earth Date: {{ rover.max_date }}</div>
      </div>
      <div class="photos">Total Photos: {{ rover.total_photos }}</div>
      <div class="cameras divide-y">
        <div class="text-lg text-white">Cameras</div>
        <div
          class="camera"
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
  name: 'Curiosity',
  data() {
    return {
      rover: {},
      loading: true,
    }
  },
  async created() {
    try {
      const res = await axios.get(
        'https://mars-photos.herokuapp.com/api/v1/rovers/Curiosity/'
      )

      this.rover = res.data.rover
      this.loading = false
    } catch (err) {
      console.log(err)
    }
  },
}
</script>

<style scoped>
.card {
  @apply flex flex-col max-w-lg rounded bg-black bg-opacity-75 px-3 py-3 items-center tracking-widest leading-tight;
}

.name {
  @apply font-bold text-2xl mb-2 text-white uppercase;
}

.launch-dates {
  @apply px-2 py-2 inline-flex  border;
}

.launch-date {
  @apply text-white px-2 text-lg;
}

.status {
  @apply text-lg text-green-500 capitalize border border-t-0 border-b-0 p-2;
}

.max-dates {
  @apply inline-flex py-2  border;
}

.max-date {
  @apply text-lg px-2 text-white;
}

.photos {
  @apply text-lg p-3 border border-t-0 border-b-0 text-white;
}

.cameras {
  @apply flex flex-col border p-3 items-center;
}

.camera {
  @apply text-base text-white tracking-widest leading-snug py-1;
}
</style>