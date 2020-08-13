<template>
  <div class="flex justify-start items-center">
    <img
      class="object-cover h-screen w-screen"
      style="filter: brightness(60%)"
      src="../static/img/cover.jpg"
      alt="Curiosity on Mars"
    />
    <div class="label md:pl-20 divide-y">
      <div class="welcome text-5xl">Welcome to Marspecto.</div>
      <div class="welcome text-4xl">satisfy your curiosity</div>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style>
.label {
  @apply absolute flex flex-col p-6;
}

.welcome {
  @apply text-white font-hairline tracking-widest;
}
</style>
