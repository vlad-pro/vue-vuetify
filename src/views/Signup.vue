<template>
  <v-container>
    <v-row>
      <v-col>
        <h1>Signup</h1>
        <v-form>
          <v-text-field
            label="Email"
            type="email"
            v-model="email"
            :rules="emailRules"
            required
          ></v-text-field>
          <v-autocomplete
            label="Which browser do you use?"
            :items="browsers"
          ></v-autocomplete>
          <v-file-input label="Attach upic"></v-file-input>
          <v-text-field
            label="Birhday"
            v-model="birthday"
            readonly="true"
          ></v-text-field>
          <v-date-picker v-model="birthday"></v-date-picker>
          <v-checkbox
            label="Agree"
            v-model="agreeToTerms"
            v-bind:rules="agreeToTermsRules"
            required
          ></v-checkbox>
          <v-btn type="submit" color="primary">Submit</v-btn>
        </v-form>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    agreeToTerms: false,
    agreeToTermsRules: [(value) => !!value || "You must agree to terms"],
    email: "",
    emailRules: [
      (value) => !!value || "Email is required",
      (value) => value.indexOf("@") !== 0 || "Email should have a username",
      (value) => value.includes("@") || "Email should be valid",
      (value) =>
        value.indexOf(".") - value.indexOf("@") > 1 ||
        "Email should contain a valid domain.",
      (value) => value.includes(".") || "Email should include a period symbol.",
      (value) =>
        value.indexOf(".") <= value.length - 3 ||
        "Email should contain a valid domain extension.",
    ],
    birthday: "",
    browsers: ["Chrome", "Firefox", "Safari", "Edge"],
  }),
};
</script>

<style></style>
