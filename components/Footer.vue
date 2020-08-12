<template>
  <div>
    <div
      class="flex flex-row bg-black bg-opacity-75 w-full justify-center items-center p-3 divide-x"
    >
      <div class="flex items-center px-3">
        <a
          href="https://api.nasa.gov/#MarsPhotos"
          target="_blank"
          class="text-white font-light text-base flex items-center"
          rel="noopener noreferrer"
        >
          <img src="../static/img/logo.png" width="44px" alt="NASA LOGO" />
          { APIs }
        </a>
      </div>

      <div class="px-3">
        <a
          href="#"
          class="text-base text-white tracking-widest"
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

<style>
</style>