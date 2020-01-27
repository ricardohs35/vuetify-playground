<template>
  <v-container>
    <v-row>
      <v-col>
        <h1>Signup</h1>
        <v-form>
          <v-text-field label="Email"></v-text-field>

          <v-autocomplete
            :items="browsers"
            label="Which browser do you use?"
          ></v-autocomplete>

          <v-file-input label="Attach profile picture"></v-file-input>

          <v-text-field
            v-model="birthday"
            label="Birthday"
            readonly
          ></v-text-field>

          <v-date-picker
            v-model="birthday"
          ></v-date-picker>

          <v-checkbox label="Agree to terms & conditions"></v-checkbox>

          <v-btn type="submit">Submit</v-btn>
        </v-form>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
  export default {
    data: () => ({
      birthday: '',

      browsers: [
        'Chrome', 'Firefox', 'Safari', 'Edge', 'Brave'
      ]
    })
  }
</script>
