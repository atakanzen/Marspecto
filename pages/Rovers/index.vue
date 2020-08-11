<template>
  <div class="flex flex-col md:flex-row h-screen justify-evenly items-center p-6 overflow-auto">
    <Curiosity />
    <Opportunity />
    <Spirit />
  </div>
</template>

<script>
import Curiosity from '../../components/Curiosity'
import Opportunity from '../../components/Opportunity'
import Spirit from '../../components/Spirit'

export default {
  head() {
    return {
      title: 'Marspecto | Rovers',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: "NASA rovers that's been sent to MARS.",
        },
      ],
    }
  },
  components: {
    Curiosity,
    Opportunity,
    Spirit,
  },
}
</script>

<style>
</style>