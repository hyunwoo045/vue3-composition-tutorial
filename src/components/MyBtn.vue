<template>
  <div
    v-bind="$attrs"
    class="btn"
    @click="hello">
    <slot></slot>
  </div>
</template>

<script>
import { onMounted } from 'vue';
export default {
  
  inheritAttrs: false,
  props: {
    color: {
      type: String,
      default: 'gray'
    }
  },
  emits: ['hello'],
  mounted() {
    console.log(this.color);
    console.log(this.$attrs)
  },
  methods: {
    hello() {
      this.$emit('hello')
    }
  },

  setup(props, context) {
    console.log("onSetup: ", context)
    onMounted(() => {
      console.log(props.color)
      console.log(context.attrs)
    })
  }
}
</script>