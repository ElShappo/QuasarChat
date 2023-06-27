<template>
  <q-layout view="hHh Lpr fFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          v-if="$route.fullPath.includes('/chat')"
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
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>

    <q-footer
      v-if="$route.fullPath.includes('/chat')"
      class="row justify-center bg-white"
    >
      <q-toolbar
        class="q-pl-none col-xs-12 col-sm-8 col-md-6 col-lg-5 bg-primary"
      >
        <q-toolbar-title class="row justify-center">
          <q-input
            outlined
            square
            bg-color="white"
            v-model="newMessage"
            placeholder="Write a message..."
            class="full-width"
          >
            <template v-slot:append>
              <q-icon
                v-if="newMessage !== ''"
                name="close"
                @click="newMessage = ''"
                class="cursor-pointer"
              />
            </template>

            <template v-slot:after>
              <q-btn round dense flat icon="send" color="white" />
            </template>
          </q-input>
        </q-toolbar-title>
      </q-toolbar>
    </q-footer>
  </q-layout>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  components: {},

  data() {
    return { newMessage: '' };
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
