<template>
  <v-container>
    <template>
      <v-toolbar color="indigo" class="mx-auto" max-width="500" dark>
        <v-toolbar-title>Sender</v-toolbar-title>
      </v-toolbar>
      <v-card class="mx-auto pa-6" max-width="500">
        <v-form ref="form" v-model="valid" lazy-validation>
          <v-text-field
            outlined
            v-model="name"
            :counter="50"
            :rules="nameRules"
            label="Name"
            required
          ></v-text-field>

          <v-text-field
            outlined
            v-model="phonenumber"
            label="Phone Number"
            required
          ></v-text-field>
          <v-text-field
            outlined
            v-model="address"
            label="Address"
            required
          ></v-text-field>
          <v-text-field
            outlined
            v-model="apartment"
            label="Apartment,suite,etc(optional)"
          ></v-text-field>
          <v-text-field
            outlined
            v-model="city"
            label="City"
            required
          ></v-text-field>
          <v-text-field
            outlined
            v-model="state"
            label="State"
            required
          ></v-text-field>
          <v-text-field
            outlined
            v-model="zipcode"
            label="Zipcode"
            required
          ></v-text-field>
          <v-select
            outlined
            v-model="country"
            :items="items"
            :rules="[(v) => !!v || 'Item is required']"
            label="Country"
            required
          ></v-select>

          <v-checkbox
            v-model="checkbox"
            :rules="[(v) => !!v || 'You must agree to continue!']"
            label="Do you agree?"
            required
          ></v-checkbox>

          <v-btn :disabled="!valid" color="success" class="mr-4" @click="save">
            Save
          </v-btn>

          <v-btn color="error" class="mr-4" @click="reset"> Reset Form </v-btn>
        </v-form>
      </v-card>
    </template>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    valid: true,
    name: "",
    phonenumber: "",
    address: "",
    apartment: "",
    city: "",
    state: "",
    zipcode: "",
    country: "",
    nameRules: [
      (v) => !!v || "Name is required",
      (v) => (v && v.length <= 10) || "Name must be less than 10 characters",
    ],
    email: "",
    emailRules: [
      (v) => !!v || "E-mail is required",
      (v) => /.+@.+\..+/.test(v) || "E-mail must be valid",
    ],
    select: null,
    items: ["Item 1", "Item 2", "Item 3", "Item 4"],
    checkbox: false,
  }),

  methods: {
    save() {
      this.$refs.form.validate();
    },
    reset() {
      this.$refs.form.reset();
    },
    resetValidation() {
      this.$refs.form.resetValidation();
    },
  },
};
</script>
