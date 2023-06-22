<template>
  <q-page class="row justify-center items-end">
    <div class="q-ma-lg col-xs-10 col-sm-7 col-md-5 bg-primary">
      <q-toolbar class="q-pl-none">
        <q-toolbar-title class="row justify-center">
          <q-input
            outlined
            square
            bg-color="white"
            v-model="text"
            placeholder="Write a message..."
            class="full-width"
          >
            <template v-slot:append>
              <q-icon
                v-if="text !== ''"
                name="close"
                @click="text = ''"
                class="cursor-pointer"
              />
            </template>

            <template v-slot:after>
              <q-btn round dense flat icon="send" color="white" />
            </template>
          </q-input>
        </q-toolbar-title>
      </q-toolbar>
    </div>
  </q-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  data() {
    return {
      text: '',
    };
  },
});
</script>
