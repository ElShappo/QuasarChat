<template>
  <q-page class="column">
    <q-banner
      inline-actions
      class="text-white bg-grey-4 text-black text-center"
    >
      User is currently offline
    </q-banner>
    <div class="col q-pa-md row justify-center">
      <div style="width: 100%; max-width: 400px" class="column justify-end">
        <q-chat-message
          v-for="message of messages"
          :key="message.text"
          :name="message.from"
          :text="[message.text]"
          :sent="message.from === 'me' ? true : false"
        />
      </div>
    </div>
    <q-footer
      v-if="$route.fullPath.includes('/chat')"
      class="row justify-center bg-white"
    >
      <q-toolbar
        class="q-pl-none col-xs-12 col-sm-8 col-md-6 col-lg-5 bg-primary"
      >
        <q-toolbar-title class="row justify-center">
          <q-form @submit="sendMessage" class="full-width">
            <q-input
              outlined
              square
              bg-color="white"
              v-model="newMessage"
              placeholder="Write a message..."
            >
              <!-- <template v-slot:append>
                <q-icon
                  v-if="newMessage !== ''"
                  name="close"
                  @click="newMessage = ''"
                  class="cursor-pointer"
                />
              </template> -->
              <template v-slot:after>
                <q-btn round dense flat icon="send" color="white" />
              </template>
            </q-input>
          </q-form>
        </q-toolbar-title>
      </q-toolbar>
    </q-footer>
  </q-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  data() {
    return {
      newMessage: '',
      messages: [
        {
          text: 'Hi Michel, you doing fine?',
          from: 'me',
        },
        {
          text: 'Thx George, I am doing just great',
          from: 'them',
        },
        {
          text: 'Awesome, Michel!',
          from: 'me',
        },
      ],
    };
  },
  methods: {
    sendMessage() {
      console.log('hey!');
      if (!/^\s*$/.test(this.newMessage)) {
        this.messages.push({
          text: this.newMessage,
          from: 'me',
        });
        this.newMessage = '';
      }
    },
  },
});
</script>
