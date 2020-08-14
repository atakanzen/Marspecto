<template>
  <div class="static grid grid-cols-5 grid-rows-5 gap-5 row-gap-5 overflow-auto">
    <img v-bind:key="photo.id" v-for="photo in this.currentPhotos" :src="photo.img_src" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentPage: 0,
      photosPerPage: 25,
      currentPhotos: [],
    }
  },
  created() {
    this.getCurrentPhotos()
  },
  props: {
    photos: Array,
  },
  methods: {
    // getCurrentPhotos() {
    //   const lastIndex = this.currentPage * this.photosPerPage
    //   const firstIndex = lastIndex - this.photosPerPage
    //   this.currentPhotos = this.$props.photos.slice(firstIndex, lastIndex)
    //   console.log(this.currentPhotos)
    // },
  },
}
</script>

<style>
</style>