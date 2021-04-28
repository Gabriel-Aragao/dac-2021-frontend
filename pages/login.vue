<template>
  <v-col cols="12" sm="8" md="6">
    <h1>Login</h1>
    <v-form ref="form">
      <v-text-field
        v-model="email"
        :rules="emailRules"
        label="E-mail"
        required
      />
      <v-text-field
        v-model="password"
        :rules="passwordRules"
        :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
        :type="showPassword ? 'text' : 'password'"
        label="Password"
        required
        @click:append="showPassword = !showPassword"
      />
    </v-form>
  </v-col>
</template>

<script>
export default {
  data () {
    return {
      email: '',
      password: '',
      showPassword: false,
      emailRules: [
        v => !v || /^\w+([.-]?\w+)*@\w+([.-]?\w+)*(\.\w{2,3})+$/.test(v) || 'E-mail must be valid'
      ],
      passwordRules: [
        v => !v || /^(?=.*[a-z])/.test(v) || 'Password must contains at least one lowercase character.',
        v => !v || /^(?=.*[A-Z])/.test(v) || 'Password must contains at least one capital letter.',
        v => !v || /^(?=.*[0-9])/.test(v) || 'Password must contains at least one number.',
        v => !v || /^(?=.*[!@#$%^&*])/.test(v) || 'Password must contains at least one special character.',
        v => !v || /^(?=.{8,})/.test(v) || 'Password must contains at least 8 characters.'
      ]
    }
  }
}
</script>
