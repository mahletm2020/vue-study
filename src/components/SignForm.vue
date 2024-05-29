<template>
  <form name="signup" >

  <label >email</label>
  <input type="email" required v-model="email">
 

  <label >password</label>
  <input type="password" required v-model="password">

  <label >role</label>
   <select    name="" id="" v-model="role">
      <option value="webdev">webdev</option>
      <option value="cyber">cyber</option>
      <option value="designer">graphics</option>
   </select>

     <label >skills</label>
     <input type="text" v-model="tempskill" @keyup.alt="addskil">
     <div v-for="skill  in skills " :key="skill"  class="pill">
      {{ skill }}
     </div>
   <div class="terms">
     <input type="checkbox" required v-model="terms">
     <label >accept termes and conditions</label>
   </div>


 </form>

     <div class="nn">
         <p>your email is: {{ email }}</p>
         <p>your password: {{ password }}</p>
          <p>and  role u selected : {{ role }}</p>
          <p>terms acceted : {{ terms }}</p>
     </div>
</template>

<script>
export default {
 data(){
  return{//remamber returen is always the iniial state of  copmonent
    email :'',
    password: '',
    role:'',
    terms: false,
    tempskill:'',
    skills:[]
  }
 },
 methods:{//obj thatcontain methods which are functions to call formtemplate or whereever to perform  action manipulate dataor reactt to events
  addskil(e){
   if(e.key === ',' && this.tempskill){
     if(!this.skills.includes(this.tempskill)){
      this.skills.push(this.tempskill)
     }
    this.tempskill = ''
   }
  }
 }
}
</script>

<style>
form{
  width: 500px;
  margin: 30px auto;
  background-color: rgb(248, 246, 244);
  text-align: left;
  padding: 30px;
  border-radius: 10px;

}
label ,option{
  color: rgb(139, 131, 119);
  display: inline-block;
  margin: 25px 0 15px;
  font-size: 1em;
}
input ,select{
  display: block;
  padding: 10px 6px;
  width: 100%;
  box-sizing: border-box;
  border: none;
  border-bottom: 1px solid wheat;
  color: #010a12;

}
.nn{
  width: 500px;
  margin: 30px auto;
  background-color: rgb(250, 238, 225);
  text-align: left;
  padding: 30px;
  border-radius: 10px;
  color: black;
}
input[type="checkbox"]{
  display: inline-block;
  width: 16px;
  margin: 0 10px 0 0;
  position: relative;
  top: 2px;
}
</style>