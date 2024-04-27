<template>
  <div class="header">
      <h1> {{phoneName}} </h1>
      <h4 id="authorname"> {{authorName}} </h4>
  </div>
</template>
  
  <script>
  
  export default{ 
      name: 'MyHeader',
      props:{ 
  
          authorName:String,
          phoneName:String,
          
      }
  }
  
  </script>
  
  <style scoped>
  
  .header{
      text-align: center;
      font-weight: bolder;
      font-size: 18px;
      color: rgb(38, 137, 142);
      font-family:'Times New Roman', Times, serif;
  }

  #authorname{
    color: black;
    font-size: 18px;
    margin-bottom: 10px;
  }
  
  </style>