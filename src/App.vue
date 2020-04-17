<template>
  <div class="container">
     <h1>Github Users Data </h1>
     <p style="text-align:center">Press the button below to view the details of GitHub Users</p>
     <table>
       <thead>
        <tr>
           <td><userData/></td>
        </tr>
       </thead>
     </table>
  </div>
</template>

<script>
import userData from '@/components/userData'
  export default{
    name:'MainCompoenent',
    components:{userData}, 
    data:()=>({
    }),
    methods:()=>{

    }
  }
</script>
<style>
.container{
  background-image:url(https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcR-h9cz7RThv0IeGf8-eKtm3gHFQPt5B-CHJRCol_hA3muwgirT&usqp=CAU);
}
h1{
  padding-top:10px;
  color:white;
}
p{
  color:white;
}
</style>
