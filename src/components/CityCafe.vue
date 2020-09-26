<template>
<div>
  {{cityCode}}

  <select v-model="cityCode">
      <option v-for="city in cities" 
      :key="city.code" 
      :value="city.code">
     
           {{city.name}}
      </option>
      </select>  

  <select v-model="regionCode">
      <option v-for="region in regions" 
      :key="region.code" 
      :value="region.code">
     
           <h1>{{region.name}}</h1>
      </option>
      </select> 


</div>
</template>

<script> 
import zip from '../zip.json';
export default {
     data: () => ({        
      zip, 
      cityCode: 100,      
     }),
computed:{
    cities() {
        return this.zip.cities;
    },
    regions() {
        return [];
    },
},
}; 
</script>