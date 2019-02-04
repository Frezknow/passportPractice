<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8">
                <div class="card">
                    <div class="card-header">Example Component</div>

                    <div class="card-body">
                      <input type="text" v-model="email" placeholder="Email"/>
                      <input type="password" v-model="password" placehold="Password"/>
                      <input type="button" v-on:click="login"/>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
       data(){
         return{
           email:'',
           password:''
         }
       },
       methods:{
         login(){
           var data = {
              client_id:2,
              client_secret:'qJG9GzvJVEZvnHBzTJTFR8QOBncKQMBfBhnWQpzv',
              grant_type:'password',
              username:this.email,
              password:this.password
          }
          alert(this.email);
          this.$http.post("/oauth/token",data).then(
            function(response){
              console.log(response)
            })

         }
       },
        mounted() {
            console.log('Component mounted.')
        }
    }
</script>
