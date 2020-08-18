<template>
  <div class="flex justify-center items-center h-screen static overflow-auto space-y-1">
    <SearchForm />
  </div>
</template>

<script>
import axios from "axios";
import SearchForm from "../../components/SearchForm";

export default {
  components: {
    SearchForm,
  },
  head() {
    return {
      title: "Marspecto | Search",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Search photos that's been taken on Mars by NASA rovers",
        },
      ],
    };
  },
};
</script>

<style scoped>
</style>