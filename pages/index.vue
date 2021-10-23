<template>
  <div class="container">
    <div>
      <logo />
      <h1 class="title">
        nuxt-mbi
      </h1>
      <h2 class="subtitle">
        My laudable Nuxt.js project
      </h2>
      <div class="links">
        <a href="https://nuxtjs.org/" target="_blank" class="button--green">
          Documentation
        </a>
        <a
          href="https://github.com/nuxt/nuxt.js"
          target="_blank"
          class="button--grey"
        >
          GitHub
        </a>
      </div>
    </div>

    <div class="sample">
      <h1>Example use of @carbon/vue</h1>
      <cv-text-input
        label="Who are you?"
        v-model="yourName"
        placeholder="your name"
      />
      <cv-button @click="onClick" class="p-0 px-0 pa-0">Hello {{ yourName }}</cv-button>
      <cv-modal :visible="visible" @modal-hidden="modalClosed">
        <template slot="title">Welcome to @carbon/vue {{ yourName }}</template>
        <template slot="content">
          <p>
            Lorem ipsum dolor sit amet, consectetur adipisicing elit, seed do
            eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim
            ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut
            aliquip ex ea commodo consequat.
          </p>
        </template>
      </cv-modal>
    </div>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  },
  data() {
    return {
      yourName: '',
      visible: false
    }
  },
  methods: {
    onClick() {
      this.visible = true
    },
    modalClosed() {
      this.visible = false
    }
  }
}
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
