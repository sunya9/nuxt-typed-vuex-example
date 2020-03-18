<template>
  <div class="container">
    <div>
      <logo />
      <h1 class="title">
        nuxt-typed-vuex-example
      </h1>
      <h2 class="subtitle">
        My super Nuxt.js project
      </h2>
      <p>message: {{ message }}</p>
      <p>reversed message: {{ reversedMessage }}</p>
      <input type="text" v-model="message" />
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Logo from '~/components/Logo.vue'

export default Vue.extend({
  components: {
    Logo
  },
  computed: {
    message: {
      get() {
         return this.$accessor.message
      },
      set(newMessage: string) {
        this.$accessor.updateMessageAction(newMessage)
      }
    },
    reversedMessage() {
      return this.$accessor.reversedMessage
    }
  }
})
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
