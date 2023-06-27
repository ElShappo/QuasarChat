<template>
  <q-layout view="hHh Lpr fFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          @click="$router.go(-1)"
          flat
          square
          color="white"
          icon="keyboard_backspace"
          label="Back"
        />
        <q-toolbar-title class="absolute-center">
          {{ title }}
        </q-toolbar-title>
        <q-btn
          flat
          to="/auth"
          square
          color="white"
          icon="account_circle"
          label="Login"
          class="absolute-right"
        />
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  components: {},

  computed: {
    title() {
      return this.$route.fullPath === '/'
        ? 'QuasarChat'
        : this.$route.fullPath === '/chat'
        ? 'Chat'
        : 'Login';
    },
  },
});
</script>
