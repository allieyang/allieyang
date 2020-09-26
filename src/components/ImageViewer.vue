<template>
<div>
    <h1>{{imageWidth}} X {{imageHeight}}
     </h1>
<img 
@load="imgLoaded"
src="https://s.yimg.com/ny/api/res/1.2/12UU2JphAsbxTTDca.7QFQ--~A/YXBwaWQ9aGlnaGxhbmRlcjtzbT0xO3c9MTA4MDtoPTcxNg--/https://media-mbst-pub-ue1.s3.amazonaws.com/creatr-uploaded-images/2019-11/7b5b5330-112b-11ea-a77f-7c019be7ecae" 
  />
  </div>
</template>

<script>
export default {
     data: () => ({
    imageWidth: 0,
    imageHeight: 0,
      }),
    methods:{
        imgLoaded(event){   
         //   const {width, height} = event.target;    
        this.imageWidth = event.target.width;
         this.imageHeight = event.target.height;
        }
    }
 };
</script>

<style>

</style>

