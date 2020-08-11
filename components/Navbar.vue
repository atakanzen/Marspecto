<template>
  <nav
    class="flex fixed w-full bg-black bg-opacity-75 justify-between p-6 items-center divide-x divide-orange-800"
  >
    <div class="items-center flex-shrink-0 text-white mr-6">
      <nuxt-link
        to="/"
        class="font-semibold text-2xl text-orange-600 tracking-widest underline"
      >Marspecto</nuxt-link>
    </div>
    <div class="inline-flex flex-grow">
      <nuxt-link to="/rovers" class="flex p-2 m-2 text-xl text-white">Rovers</nuxt-link>
      <nuxt-link to="/search" class="flex p-2 m-2 text-xl text-white">Search</nuxt-link>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'Navbar',
}
</script>

<style>
</style>