<template>
  <div>
  <h1>Image Slider</h1>
   <div class="container">
   <img  v-bind:src="currentImage">
     
   </div>
 </div>
  
</template>

<script>
export default {
  name: 'HelloWorld',
  data :()=>({
    imageList:["Tulips.jpg","Penguins.jpg","Lighthouse.jpg","Koala.jpg","Jellyfish.jpg"] ,
    currentImage : "",
    imageIndex : 0,

  }),
  created(){
    this.currentImage = this.imageList[0]
    this.slideImage()
  },
  methods:{
    slideImage(){
      var that = this

       setInterval(function(){
        if(that.imageIndex == that.imageList.length -1){
          that.imageIndex = -1 
        }
        that.imageIndex = that.imageIndex + 1
        that.currentImage = that.imageList[that.imageIndex]
      },2000)
    },

    

  },
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container{
  width: 700px;
  border:1px solid black;

  margin:auto;
}


img{
  height:100%;
  width:100%;


  
}
</style>
