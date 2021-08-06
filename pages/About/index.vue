<template>
  <div class="flex items-center justify-center p-6 md:h-screen">
    <div>
      <div class="bg-black bg-opacity-75 p-16 rounded">
        <div class="font-light tracking-wider text-xl text-white p-2 leading-relaxed">
          Ever wondered what is going on at Mars right now?
          Well I did, so I decided to develop this project. With some research I found resources that I could use. Thanks to
          <a
            href="https://api.nasa.gov/"
            target="_blank"
            class="font-medium"
          >NASA { APIs }</a> I was able to use their data. So here it goes, a website that can access a database full of Martian mission photos by the NASA rovers. You can always contact me from my
          <a
            href="https://twitter.com/atakanzen_"
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
  head() {
    return {
      title: "Marspecto | About",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "About website and author.",
        },
      ],
    };
  },
  name: "About",
};
</script>

<style>
</style>
