<template>
  <q-form @submit="onSubmit" @reset="onReset" class="q-gutter-lg">
    <q-input
      v-if="tab === 'register'"
      filled
      v-model="name"
      label="Name"
      lazy-rules
      :rules="nameRules"
    />

    <q-input
      filled
      v-model="email"
      label="Email"
      type="email"
      lazy-rules
      :rules="emailRules"
    />

    <q-input
      filled
      v-model="password"
      label="Password"
      lazy-rules
      type="password"
      :rules="passwordRules"
    />

    <div>
      <q-btn label="Submit" type="submit" color="primary" />
      <q-btn label="Reset" type="reset" color="primary" flat class="q-ml-sm" />
    </div>
  </q-form>
</template>

<script>
export default {
  props: ['tab'],
  data() {
    return {
      name: '',
      email: '',
      password: '',
      accept: false,

      nameRules: [(val) => (val && val.length > 0) || 'Name cannot be empty'],
      emailRules: [(val) => /^.+@.+$/.test(val) || 'Invalid email'],
      passwordRules: [
        (val) => (val && val.length > 5) || 'More than 6 symbols are required',
      ],
    };
  },
  methods: {
    onSubmit() {
      if (this.tab === 'register') {
        console.log('register, submitted');
      } else {
        console.log('login, submitted');
      }
    },

    onReset() {
      this.name = '';
      this.email = '';
      this.password = '';
      this.accept = false;
    },
  },
};
</script>
