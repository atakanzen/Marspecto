<template>
  <nav class="navbar">
    <div class="links divide-x divide-orange-600 space-x-4">
      <div>
        <nuxt-link to="/" class="homelink md:text-2xl">Marspecto</nuxt-link>
      </div>
      <div class="inline-flex flex-grow">
        <nuxt-link to="/rovers" class="link lg:text-xl md:pl-5">Rovers</nuxt-link>
        <nuxt-link to="/search" class="link lg:text-xl md:pl-5">Search</nuxt-link>
        <nuxt-link to="/about" class="link lg:text-xl md:pl-5">About</nuxt-link>
      </div>
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
  @apply flex  w-screen bg-black bg-opacity-75 justify-between p-4 items-center;
}
.links {
  @apply flex items-center flex-shrink-0 text-white;
}
.homelink {
  @apply font-semibold text-xl text-orange-600 tracking-widest underline;
}
.link {
  @apply flex pl-3 text-lg text-white;
}
</style>