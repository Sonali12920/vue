<template>
    <div> 
        <button v-on:click="fetchData" > Show Data</button>
        <div v-if="loader">
            <p>Collecting data...</p>
        </div>
        <table border="3">
            <thead>
                <tr style="background-color:  lightgray; width:70px; height:40px;">
                    <td>Login</td>
                    <td>ID</td>
                    <td>PROFILE LINKS</td>
                </tr>
            </thead>
            <tbody>
                <tr v-for="(user,index) in userData" :key="index" style="background-color: whitesmoke; width:70px; height:30px;">
                    <td>{{user.login}}</td>
                    <td>{{user.id}}</td>
                    <td>{{user.html_url}}</td>
                </tr>
            </tbody>
        </table>
  </div>
</template>

<script>
  export default{
    name:'userData',
   data:()=>({
       userData:[],
        loader:false,
   }),
   methods:{
       fetchData(){
             this.loader = true
           fetch('https://api.github.com/users').then(res=>res.json()).then(data=>{
               console.log(data)
               this.userData=data
                 this.loader = false
           }).catch(e=>{
               console.log(e)
           })
          }   
       }
  }
</script>

<style>
button{
  background-color:lightblue;
  margin:40px 670px;
  width:150px;
  height:40px;
  align-content: center;
  border-style: groove;
}
table{
    border: rgb(80, 80, 80);
    box-shadow: lightgray;
    margin: 15px auto ;
    width:70%;
    max-height: 1000px;
    text-align: center; 
}
button:hover{
    background-color: black;
    color: whitesmoke;
}
h1{
    text-align: center;
    color: rgb(12, 12, 12);
}
</style>