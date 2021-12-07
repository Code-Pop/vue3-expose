<template>
  <MyCounter ref="counter" />

  <button @click="reset">Reset from parent</button>
  <button @click="terminate">Terminate from parent</button>
</template>

<script>
import MyCounter from '@/components/MyCounter.vue'

export default {
  name: 'App',
  components: {
    MyCounter
  },
  methods: {
    reset () {
      this.$refs.counter.reset()
    },
    terminate () {
      this.$refs.counter.terminate()
    }
  }
}
</script>
