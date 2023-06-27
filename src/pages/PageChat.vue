<template>
  <q-page class="row justify-center items-end">
    <div class="q-pa-md row justify-center col-12">
      <div style="width: 100%; max-width: 400px">
        <q-chat-message name="me" :text="['hey, how are you?']" sent />
        <q-chat-message name="Jane" :text="['doing fine, how r you?']" />
        <q-chat-message name="Jane" :text="['doing fine, how r you?']" />
        <q-chat-message name="Jane" :text="['doing fine, how r you?']" />
        <q-chat-message name="Jane" :text="['doing fine, how r you?']" />
        <q-chat-message name="Jane" :text="['doing fine, how r you?']" />
        <q-chat-message name="Jane" :text="['doing fine, how r you?']" />
        <q-chat-message name="Jane" :text="['doing fine, how r you?']" />
        <q-chat-message name="Jane" :text="['doing fine, how r you?']" />
        <q-chat-message name="Jane" :text="['doing fine, how r you?']" />
        <q-chat-message name="Jane" :text="['doing fine, how r you?']" />
        <q-chat-message name="Jane" :text="['doing fine, how r you?']" />
        <q-chat-message name="Jane" :text="['doing fine, how r you?']" />
        <q-chat-message name="Jane" :text="['doing fine, how r you?']" />
        <q-chat-message name="Jane" :text="['doing fine, how r you?']" />
      </div>
    </div>
  </q-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  data() {
    return {
      newMessage: '',
    };
  },
});
</script>
