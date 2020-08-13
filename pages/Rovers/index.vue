<template>
  <div
    class="flex flex-col justify-between items-center p-10 lg:flex-row space-y-12 lg:space-y-0 lg:space-x-12 overflow-auto"
  >
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