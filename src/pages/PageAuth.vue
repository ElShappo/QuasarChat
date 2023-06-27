<template>
  <q-page class="row flex-center">
    <q-card class="col q-pa-xl" style="width: 100%; max-width: 600px">
      <q-tabs
        v-model="tab"
        dense
        class="text-grey row items-center q-pb-lg"
        active-color="primary"
        indicator-color="primary"
        align="justify"
        narrow-indicator
      >
        <q-tab name="login" label="Login" />
        <q-tab name="register" label="Register" />
      </q-tabs>

      <q-separator />

      <q-tab-panels v-model="tab" animated class="q-pt-md">
        <q-tab-panel name="login">
          <q-form @submit="onSubmit" @reset="onReset" class="q-gutter-lg">
            <q-input
              filled
              v-model="name"
              label="Name"
              lazy-rules
              :rules="[
                (val) => (val && val.length > 0) || 'Please type something',
              ]"
            />

            <q-input
              filled
              v-model="email"
              label="Email"
              lazy-rules
              :rules="[
                (val) => (val && val.length > 0) || 'Please type something',
              ]"
            />

            <div>
              <q-btn label="Submit" type="submit" color="primary" />
              <q-btn
                label="Reset"
                type="reset"
                color="primary"
                flat
                class="q-ml-sm"
              />
            </div>
          </q-form>
        </q-tab-panel>

        <q-tab-panel name="register">
          <q-form @submit="onSubmit" @reset="onReset" class="q-gutter-lg">
            <q-input
              filled
              v-model="name"
              label="Name"
              lazy-rules
              :rules="[
                (val) => (val && val.length > 0) || 'Please type something',
              ]"
            />

            <q-input
              filled
              v-model="email"
              label="Email"
              lazy-rules
              :rules="[
                (val) => (val && val.length > 0) || 'Please type something',
              ]"
            />

            <q-input
              filled
              v-model="password"
              label="Password"
              lazy-rules
              :rules="[
                (val) =>
                  (val && val.length > 6) || 'More than 6 symbols are required',
              ]"
            />

            <div>
              <q-btn label="Submit" type="submit" color="primary" />
              <q-btn
                label="Reset"
                type="reset"
                color="primary"
                flat
                class="q-ml-sm"
              />
            </div>
          </q-form>
        </q-tab-panel>
      </q-tab-panels>
    </q-card>
  </q-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  data() {
    return {
      tab: 'login',
      name: '',
      email: '',
      password: '',
      accept: false,
    };
  },
  methods: {
    onSubmit() {
      this.$q.notify({
        color: 'green-4',
        textColor: 'white',
        icon: 'cloud_done',
        message: 'Submitted',
      });
    },

    onReset() {
      this.name = '';
      this.email = '';
      this.password = '';
      this.accept = false;
    },
  },
});
</script>
