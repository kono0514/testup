<template>
  <v-form
    ref="form"
    v-model="valid"
    class="irs-form mt-10">
    <v-container>
      <v-layout
        column
        wrap>
        <v-flex>
          <h1 class="headline">Form W-9</h1>
          <p class="py-4">
            Please see the <a href="#" class="irs-link">instructions from the IRS</a>
            to fill out this form
          </p>
        </v-flex>
        <v-flex xs6>
          <v-text-field
            v-model="name"
            :rules="nameRules"
            label="1. Name (as shown on your income tax return)"
            placeholder=" "
            required>
          </v-text-field>
          <v-btn class="mt-4" :disabled="!valid" @click="submit">submit</v-btn>
        </v-flex>
      </v-layout>
    </v-container>
  </v-form>
</template>

<script>
export default {
  name: 'W9Form',

  data: () => ({
    valid: false,
    name: '',
    nameRules: [
      v => !!v || 'Name is required!',
    ],
  }),

  methods: {
    submit() {
      if (this.$refs.form.validate()) {
        alert('Submit');
      }
    },
  },
};
</script>

<style lang="scss">
.irs-form {
  p {
    color: #707070;
  }

  a.irs-link {
    color: #000000;
  }

  .v-label {
    font-size: 1.2em;
    color: rgba(0, 0, 0, 0.87)!important;
  }
}

</style>
