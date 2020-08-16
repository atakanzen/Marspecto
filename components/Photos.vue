<template>
  <div class="flex flex-col items-center justify-center">
    <div
      v-if="!this.loading"
      class="flex flex-col items-center justify-center space-y-3 md:grid md:grid-cols-2 md:grid-rows-2 md:gap-5 lg:grid lg:grid-cols-5 lg:grid-rows-3 lg:gap-5 lg:row-gap-5"
    >
      <a :href="photo.img_src" v-bind:key="photo.id" v-for="photo in photos" target="_blank">
        <img :src="photo.img_src" class="w-64 h-64" />
      </a>
    </div>
    <div v-else>
      <Spinner />
    </div>
  </div>
</template>

<script>
import Spinner from "./Spinner";

export default {
  props: {
    photos: Array,
    loading: Boolean,
  },
  name: "Photos",
  components: {
    Spinner,
  },
};
</script>

<style scoped>
</style>