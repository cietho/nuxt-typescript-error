<template>
  <div>
    foo: {{ foo }}
    bar: {{ bar }}
  </div>
</template>

<script lang="ts">
import Vue, { PropType } from 'vue'

export default Vue.extend({
  name: 'TsComponent',
  props: {
    foo: {
      type: String as PropType<string>,
      default: 'foo'
    }
  },
  computed: {
    bar () {
      return this.foo + 'bar'
    }
  },
  mounted () {
    console.log(this.foo)
    console.log(this.bar)
    console.log(this.$axios)
    console.log(this.$el)
  }
})
</script>
