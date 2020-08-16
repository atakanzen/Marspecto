<template>
  <div>
    <div class="footer divide-x">
      <div class="px-3">
        <a
          href="https://api.nasa.gov/#MarsPhotos"
          target="_blank"
          class="logo"
          rel="noopener noreferrer"
        >
          <img src="../static/img/logo.png" width="44px" alt="NASA LOGO" />
          { APIs }
        </a>
      </div>

      <div class="px-3">
        <a
          href="https://twitter.com/atakanzzengin"
          class="author"
          target="_blank"
          rel="noopener noreferrer"
        >Atakan Zengin</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Footer',
}
</script>

<style scoped>
.footer {
  @apply flex flex-row bg-black bg-opacity-75 w-full justify-center items-center p-3;
}
.logo {
  @apply text-white font-light text-base flex items-center;
}
.author {
  @apply text-base text-white tracking-widest;
}
</style>