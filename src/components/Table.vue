<template>
  <v-container>
       <TableInput @input="add"/>
    <v-data-table 
    :items="people" 
    :headers="headers" >
    <template #[`item.picture`]="{value}">
        <v-avatar>
           <v-img :src="value"/>
        </v-avatar>
    </template>
    </v-data-table>   
  </v-container>
</template>

<script>
import people from "../people.json";
import TableInput from "./TableInput";

export default {
    components:{
     TableInput
    },
  data: () => ({
    people,
  }),
  computed: {
    headers() {
      return [
          { text: "Picture", value: "picture" },
          { text: "姓名", value: "name" },
          { text: "E-mail", value: "email" },
          { text: "性別", value: "gender" },
          { text: "年齡", value: "age" }
      ];
    },
  },
  methods:{
      add(person){
  this.people.unshift(person)
      }
  }
};
</script>