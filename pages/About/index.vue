<template>
  <div class="flex items-center justify-center h-screen overflow-auto">
    <div class="static">
      <div class="bg-black bg-opacity-75 p-16 rounded">
        <div class="font-hairline tracking-wider text-xl text-white p-2 leading-relaxed">
          Ever wondered what is going on at Mars right now?
          Well I did, so I decided to develop this project. With some research I found resources that I could use. Thanks to
          <a
            href="https://api.nasa.gov/"
            target="_blank"
            class="font-light"
          >NASA { APIs }</a> I was able to use their data. So here it goes, a database full of Martian mission photos by the NASA rovers. You can always contact me from my
          <a
            href="https://twitter.com/atakanzzengin"
            target="_blank"
            class="underline"
          >twitter</a>. Enjoy it and stay curious!
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "About",
};
</script>

<style>
</style>