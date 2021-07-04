<template>
  <div id="app">
    <Counter name="C1" :initCount="5" @emitUp="getEvent" />
    <Counter name="C2" :initCount="10" @emitUp="getEvent" />
    <p>
      EventStack:
      {{ stack }}
    </p>
  </div>
</template>

<script>
import Counter from '@/components/Counter.vue'
export default {
  components: {
    Counter
  },
  data() {
    return {
      stack: []
    }
  },
  methods: {
    getEvent(payload) {
      this.stack.push(payload)
    }
  }
}
</script>
