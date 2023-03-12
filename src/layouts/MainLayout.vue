<template>
  <q-layout view="lHh Lpr lFf">
    <q-header>
      <div class="container">
        <div class="logo q-pl-md">
          <img
            alt="Rebillion logo"
            src="~assets/logo.png"
          >
        </div>
      </div>
    </q-header>

    <q-page-container>
      <div class="container">
        <router-view />
      </div>
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'MainLayout',
  components: {
  },
  setup () {
    return {
    }
  }
})
</script>
