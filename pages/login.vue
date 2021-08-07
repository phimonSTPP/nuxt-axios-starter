<template>
  <div class="form-login">
      <input type="text" v-model="username" placeholder="username"/>
      <input type="password" v-model="password" placeholder="password"/>
      <input type="checkbox" v-model="remember"/> remember
      <input type="button" @click="login()" value="Login"/>
      {{username}}
      {{password}}
      {{remember}}
  </div>
</template>

<script>
export default {
layout: 'blank',
data(){
    return {
        username: 'mon',
        password:'1234',
        remember:false
    }
},
methods:{
    login(){
        if(this.username==='mon' && this.password=='1234'){
            alert('hi '+ this.username)
        this.$router.push('/')

        }else{
            alert('fuck!!!!!')
        }
        
    },
},

}
</script>

<style>
input{
    pading: 5px 10px;
}
input:focus{
    background-color: burlywood;
    color:white;
    
}
.form-login{
    max-width: 400px;
    max-height: 500px;
    margin: 0 auto;
    background-color: rgb(198, 236, 241) ;
    border-radius:10px;
    box-shadow: rgb(238, 220, 197);
    padding: 20px;
}

</style>