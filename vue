<script setup>
import { ref } from 'vue'
var regex =  /^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
let max_len  = ref();
let msg = ref("");
let mss = ref("");
const name = ref("");
       function validate(name){
            
       if(regex.test(this.name) && this.name.length >= this.max_len)
       {    
            this.msg = "*Valid";
            this.mss=  " * Max letters "+this.max_len+" but your letters "+this.name.length;
            
       }
       else if(this.name == "")
       {
            this.msg= "";
             this.mss=  "";
       }
       else
       {
            this.msg="*Invalid";
            this.mss=  " * Max letters "+this.max_len+" but your letters "+this.name.length;
       }

       
}

    

</script>


<template>
<div class="form">
     <div class="lab">
        <label id="Lable"> E-mail *</label>
        <input title="Enter an email" type="text" placeholder="Enter the mail id"  id="EEmail" v-model="name" @change="validate(name,max_len=7)" >   <!--@click="validate(name)"-->
        <input title="Enter an email" type="text" placeholder="Enter the mail id"  id="Email" v-model="names" @change="validate(name,max_len=5)" > 
        <input title="Enter an email" type="text" placeholder="Enter the mail id"  id="mail" v-model="named" @change="validate(name,max_len=2)" > 
     </div>
     <h2 id="message"> {{ msg }} </h2>
     <h2 id="message"> {{ mss }} </h2>
</div>

</template>
<style scope>

#EEmail{
    padding: 10px;
    box-sizing: border-box;
    margin-top: 10%;
    margin-left: 10%;
    height: 40px;
    width: 300px;
    border-radius: 50px;
    position: absolute;
    box-shadow: 1px 1px 1px 1px #888888;
}
#Email{
    padding: 10px;
    box-sizing: border-box;
    margin-top: 30%;
    margin-left: 10%;
    height: 40px;
    width: 300px;
    border-radius: 50px;
    position: absolute;
    box-shadow: 1px 1px 1px 1px #888888;
}
#mail{
    padding: 10px;
    box-sizing: border-box;
    margin-top: 50%;
    margin-left: 10%;
    height: 40px;
    width: 300px;
    border-radius: 50px;
    position: absolute;
    box-shadow: 1px 1px 1px 1px #888888;
}
.lab{
    display: flex;
    flex-direction: column;
}
#Lable{
    margin-top: 4%;
    margin-left: 13%;
    display: absolute;
    font-weight: bold;
}
#message{
    margin-left: 85%;
    color: red;
    border: 0.5px ;
    font-size: 0.7em;
}
.form{
    border-radius: 15px;
    margin-left: 750px;
    position : absolute;
    height: 300px;
    width:400px;
    box-shadow: 2px 2px 5px 5px #888888;
}

</style>

