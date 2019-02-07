<template>
  <v-form v-model="isFormValid">
    <v-container>
      <v-layout row wrap>
        <v-flex md6 offset-md3>
          <v-text-field v-model="name" :rules="rules.nameRules" label="Name" required></v-text-field>
        </v-flex>
        <v-flex md6 offset-md3>
          <v-text-field v-model="email" :rules="rules.emailRules" label="E-mail" required></v-text-field>
        </v-flex>
        <v-flex md6 offset-md3>
          <v-btn @click="" :disabled="!isFormValid" color="primary">Submit</v-btn>
        </v-flex>
      </v-layout>
    </v-container>
  </v-form>
</template>

<script>
export default {
  name: 'HelloWorld',
  data: function () {
    return {
      isFormValid: false,
      name: '',
      email: '',
      rules: {
        nameRules: [
          v => !!v || 'Name is required',
        ],
        emailRules: [
          v => !!v || 'E-mail is required',
          v => /.+@.+/.test(v) || 'E-mail must be valid'
        ]
      }
    }
  }
}
</script>
