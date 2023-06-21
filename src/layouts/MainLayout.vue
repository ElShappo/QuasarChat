<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-toolbar-title class="absolute-center">
          {{ title }}
        </q-toolbar-title>
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

  data() {
    return {};
  },

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
