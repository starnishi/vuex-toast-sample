<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <p>
      bootstrap-vue b-toast / b-toaster sample
    </p>
    <div>
      <b-button variant="primary" @click="makeToast('primary')" class="mb-2">Primary</b-button>
      <b-button @click="toast('ああ b-toaster-top-center', true)" class="mb-2">b-toaster-top-center</b-button>
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      counter: 0
    }
  },
  methods: {
    makeToast(variant = null) {
      this.$bvToast.toast('Toast body content', {
        title: `Variant ${variant || 'default'}`,
        variant: variant,
        solid: true
      })
    },
    toast(toaster, append = false) {
      this.counter++
      this.$bvToast.toast(`Toast ${this.counter} body content`, {
        title: `Toaster ${toaster}`,
        toaster: toaster,
        autoHideDelay: 50000,
        solid: true,
        appendToast: append
      })
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
