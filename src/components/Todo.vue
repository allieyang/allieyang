<template>
  <div>
     
    <input v-model="text" />
    <button @click="add" :disabled="!text">Add </button>
    <br/>
    <h2 :class="{red: invalid }">
         {{textLength}}
         </h2>
    <ul id="list">
      <li
      :class="{grey: item.done}"   
        v-for="item in list" 
      :key="item.text" 
      >
      <input type="checkbox"
      v-mode="item.done"
      />
           {{ item.text }}
      </li>
    </ul>

  </div>
</template>

<script>
export default {
  data: () => ({
    text: "",
    list: [],
  }),
computed:{
    textLength()
{ return this.text.length;
},
invalid(){
    //invalid()
   return this.text.length <=0||this.text.length > 10;
}
},

 methods: {
    add() {
      if(!this.invalid) return;
     // if(this.isRed) return;
      const item ={
          text: this.text,
          done: false,
      };
      this.list.push(item);
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

