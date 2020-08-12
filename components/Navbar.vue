<template>
  <nav
    class="flex relative w-full bg-black bg-opacity-75 justify-between p-3 items-center divide-x divide-orange-800"
  >
    <div class="items-center flex-shrink-0 text-white mr-6">
      <nuxt-link
        to="/"
        class="font-semibold text-2xl text-orange-600 tracking-widest underline"
      >Marspecto</nuxt-link>
    </div>
    <div class="inline-flex flex-grow">
      <nuxt-link
        to="/rovers"
        v-on:click.prevent="toggle"
        class="flex p-2 m-2 text-xl text-white"
      >Rovers</nuxt-link>
      <nuxt-link to="/search" class="flex p-2 m-2 text-xl text-white">Search</nuxt-link>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'Navbar',
  methods: {
    toggle: function (e) {},
  },
}
</script>

<style >
.nuxt-link-active {
  @apply underline;
}
</style>