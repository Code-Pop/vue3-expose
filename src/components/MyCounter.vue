<script>
import { ref, h } from 'vue'

export default {
  setup (props, context) {
    const counter = ref(0)

    const interval = setInterval(() => {
      counter.value++
    }, 1000)

    const reset = () => {
      counter.value = 0
    }

    const terminate = () => {
      clearInterval(interval)
    }

    context.expose({ reset })

    return () => h('div', [
      h('p', `Counter: ${counter.value}`),
      h('button', { onClick: reset }, 'Reset'),
      h('button', { onClick: terminate }, 'Terminate')
    ])
  }
}
</script>