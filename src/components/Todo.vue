<template>
  <div>
    <input v-model="text" />
    <button> @clickAdd</button>
    {{ text }}
    <ul>
      <li v-for="item in list" :key="item">
        {{ item }}
      </li>
    </ul>
    {{ text }}
  </div>
</template>

<script>
export default {
  data: () => ({
    text: "",
    list: ["a", "b", "c"],
  }),
 methods: {
    add() {
      if(!this.text)
      this.list.push(ghis.text);
      this.text = "";
      },
   },
};
</script>
<style scoped>
</style>

