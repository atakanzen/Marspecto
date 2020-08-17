<template>
  <nav class="flex static bg-black bg-opacity-75 w-screen px-2 items-center justify-center">
    <ul class="flex items-center justify-center">
      <li
        v-bind:key="page"
        v-for="page in this.pageNumbers"
        class="text-orange-700 border-orange-700 text-lg px-2"
      >
        <button v-on:click="paginate(page), getPhotos()" type="click">{{ page }}</button>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: "Pagination",
  props: ["photosPerPage", "totalPhotos", "paginate", "getPhotos"],
  data() {
    return {
      pageNumbers: [],
    };
  },

  created() {
    for (
      let i = 1;
      i <= Math.ceil(this.$props.totalPhotos / this.$props.photosPerPage);
      i++
    ) {
      this.pageNumbers.push(i);
    }
  },
};
</script>

<style>
</style>