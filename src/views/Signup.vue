<template>
<v-container>
  <v-row>
    <v-col>
      <h1>Signup</h1>
      <v-form>
        <v-text-field label="Email" type="email"></v-text-field>
        <v-autocomplete label="Which browser do you use?" :items="browsers"></v-autocomplete>
        <v-file-input label="Attach upic"></v-file-input>
        <v-text-field label="Birhday" v-model="birthday" readonly="true"></v-text-field>
        <v-date-picker v-model="birthday" ></v-date-picker>
        <v-checkbox label="Agree"></v-checkbox>
        <v-btn type="submit" color="primary">Submit</v-btn>
      </v-form>
    </v-col>
  </v-row>
</v-container>
</template>

<script>
export default {
data: () => ({
  birthday: "",
  browsers: ["Chrome","Firefox", "Safari", "Edge"]
})
}
</script>

<style>

</style>