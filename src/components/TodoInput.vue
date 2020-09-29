<template>
<v-form @submit.prevent="add">
  <v-container>
    <v-row>
      <v-col cols="9">    
      <v-text-field v-model="text" />
      </v-col>
      <v-col cols="3">
      <v-btn type="submit" :disabled="invalid">Add</v-btn>
      </v-col>
    </v-row>
  </v-container>
  </v-form>
</template>

<script>
export default {
  data: () => ({
    text: "",
  }),
  computed: {
    invalid() {
      return this.text.length <= 0 || this.text.length > 10;
    },
  },
  methods: {
    add() {
      if (this.invalid) return;
      this.$emit("input", this.text);
      this.text = "";
    },
  },
};
</script>

<style scoped>
.grey {
  color: #ddd;
}
.red {
  color: red;
}
</style>

