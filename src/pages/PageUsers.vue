<template>
  <q-page class="row q-pa-lg">
    <q-list separator class="full-width">
      <q-item
        v-for="user in users"
        :key="user.id"
        class="row justify-center"
        clickable
        v-ripple
        to="/chat"
      >
        <q-item-section avatar>
          <q-avatar color="primary" text-color="white">
            {{ user.name[0] }}
          </q-avatar>
        </q-item-section>

        <q-item-section>
          <q-item-label>{{ user.name }}</q-item-label>
        </q-item-section>

        <q-item-section side>
          <q-badge :color="user.isOnline ? 'blue-12' : 'grey-6'">
            {{ user.isOnline ? 'Online' : 'Offline' }}
          </q-badge>
        </q-item-section>
      </q-item>
    </q-list>
  </q-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  data() {
    return {
      users: [
        {
          id: 1,
          name: 'Michel',
          isOnline: true,
        },
        {
          id: 2,
          name: 'Martin',
          isOnline: true,
        },
        {
          id: 3,
          name: 'Steven',
          isOnline: false,
        },
        {
          id: 4,
          name: 'Helen',
          isOnline: true,
        },
      ],
    };
  },
});
</script>
