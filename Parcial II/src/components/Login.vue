<template>
    <div >
    
    <div class="center">
    <div class="container" style="text-align:center">
    <div class="row">
        </div>
<i class="material-icons md-48">account_circle</i>
        <h3>Ingresar cuenta </h3>
        <form class="pt-2">
  
  <div class="form-group">
   
    <input type="text" class="form-control" id="user" placeholder="Usuario">
    <br>
     <input type="password" class="form-control" id="password" placeholder="Contraseña">
  </div>
 
  <button type="submit" class="btn mainbut btn-block">Login</button>
</form>

    </div>

    </div>
    </div>
</template>



<script> 
export default {
    name: 'Login',
    data() {
        return {
            username: '',
            password: '',
            error: ''
        }
    },
    methods: {
        login() {
            this.$store.dispatch('login', {
                username: this.username,
                password: this.password
            }).then(() => {
                this.$router.push('/')
            }).catch(err => {
                this.error = err.response.data.message
            })
        }
    }
}
    


</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.mainback{
 background: linear-gradient(rgba(255, 255, 255, 0.35), rgba(255, 253, 253, 0.446)), url(/assets/user.png) no-repeat center/cover;
}

input {
    border: 2px solid #3fa6ff;
    font-size: 30px;
}
h2{
    font-size: 28px;
}
.btText{
    font-size: 10px;
}
.mainbut{
 background-color:#3fa6ff;
 font-size: 28px;
 color: white;
}
hr {
 border: 1px solid rgb(8, 67, 126);
}
h3 {
    color: #288ee7;
}
a {
    color: #226485;
}
.center{
 position: absolute;
  left: 50%;
  top: 50%;
  -webkit-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
  
}

.material-icons.md-48 { font-size: 78px;
color : #3fa6ff;
}


</style>