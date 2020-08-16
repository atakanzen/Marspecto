<template>
  <nav class="navbar divide-x divide-orange-800">
    <div class="links">
      <nuxt-link to="/" class="homelink">Marspecto</nuxt-link>
    </div>
    <div class="inline-flex flex-grow">
      <nuxt-link to="/rovers" class="link">Rovers</nuxt-link>
      <nuxt-link to="/search" class="link">Search</nuxt-link>
      <nuxt-link to="/about" class="link">About</nuxt-link>
    </div>
  </nav>
</template>

<script>
export default {
  name: "Navbar",
};
</script>

<style scoped >
.nuxt-link-active {
  @apply underline;
}
.navbar {
  @apply flex relative w-full bg-black bg-opacity-75 justify-between p-3 items-center;
}
.links {
  @apply items-center flex-shrink-0 text-white mr-6;
}
.homelink {
  @apply font-semibold text-2xl text-orange-600 tracking-widest underline;
}
.link {
  @apply flex p-2 m-2 text-xl text-white;
}
</style>