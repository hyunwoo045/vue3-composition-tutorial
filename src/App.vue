<template>
  <h1 @click="increase">
    {{ count }} / {{ doubleCount }}
  </h1>
  <h1 @click="changeMessage">
    {{ message }} / {{ reversedMessage }}
  </h1>
</template>


<script>
export default {
  data() {
    return {
      count: 0,
      message: 'Hello World!',
    }
  },
  computed: {
    doubleCount() {
      return this.count * 2
    },
    reversedMessage() {
      return this.message.split('').reverse().join('')
    }
  },
  watch: {
    message(newValue) {
      console.log(newValue)
    }
  },
  created() {
    console.log(this.message);
  },
  mounted() {
    console.log(this.count);
  },
  methods: {
    increase() {
      this.count += 1
    },
    changeMessage() {
      this.message = 'Good?!'
    }
  }
}
</script>


<style scoped>
h1 {
  width: 600px;
  background-color: royalblue;
  font-size: 50px;
  padding: 10px;
  text-align: center;
  margin: 10px;
}
</style>