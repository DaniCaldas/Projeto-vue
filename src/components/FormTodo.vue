<template>

       <br>
       <div class="ContainerInput">
       <h4>Nome</h4>
       <input class="input-name" placeholder="Daniel Caldas" type="text" v-model="Nome">
       
       <br> <br>

       <h4>Telefone

       </h4>
       <input class="input-number" type="text" placeholder="(00)0000-0000" maxlength="12"  v-model='Telefone'>
       <br> <br>  
          <h4>E-mail</h4>
        <input type="email" class="input-email" placeholder="exemple@gmail.com" v-model="email">
       <br><br>

       <button class="btn-primary" v-on:click="Logar">Submit</button>

    </div>
  
       <br>
       <br>

</template>

<style scoped>
/*css de requisições */
.input-name:focus{
    background-color: whitesmoke;
    caret-color: red;
}
.input-number:focus{
    background-color: whitesmoke;
    caret-color: red;
}
.input-name:hover{
     cursor: pointer;
}
.input-name:invalid{
       border-color: red;
    box-shadow: 0px 0px 3px crimson;
}
.input-name:focus:invalid{
    outline: none;
}

.input-number:hover{
    cursor: pointer;
}
.input-number:invalid{
       border-color: red;
    box-shadow: 0px 0px 3px crimson;
}
.input-number:focus:invalid{
    outline: none;
}


.btn-primary{
    width: 120px;
    border-radius:4px ;
}
.btn-primary:hover{
    transition: .6s;
}


.input-email:focus{
   background-color: whitesmoke;
    caret-color: red;
}
.input-email:hover{
    cursor: pointer;
}
.input-email:invalid{
    border-color: red;
    box-shadow: 0px 0px 3px crimson;
}
.input-email:focus:invalid{
    outline: none;
} 

</style>



<style scoped>
/*css simples */

.ContainerInput{
    margin:0 auto;
    background-color: #4b9093;
    width: 20em;
    height: 26em;
    border-radius: 7px ;
}
input{
    border-color: transparent;
    width: 13em;
    height: 2.2em;
    margin-top: 10px;
}
button{
    margin-top: 13px;
    width: 2em;
}
</style>


<script>
export default {
     data(){
         return{
               Nome:'',
                Telefone:'',
                email:''
         }
     },
             methods:{
            Logar(){
                if(this.Nome == '' && this.Nome == 0)
                {
                    window.alert('Nome inválido')


                    //limpeza padrão 
                    this.Nome=''
                    this.Telefone=''
                    this.email=''
                }
                if (this.Telefone == '' && this.Telefone == 0) {
                    window.alert('Telefone inválido')

                    //limpeza padrão 
                    this.Nome=''
                    this.Telefone=''
                    this.email=''
                } 
                if (this.email == '' && this.email == 0 ) {
                    window.alert('Email inválido')

                    //limpeza padrão 
                    this.Nome=''
                    this.Telefone=''
                    this.email=''
                } 
               
                else{
                //método para mostrar os dados diretamente ao clicar no botão
                this.$emit('add-todo',{
                    Nome:this.Nome,
                    Telefone:this.Telefone,
                    email:this.email,
                
                });
                    this.Nome=''
                    this.Telefone=''
                    this.email=''
            }
        }

        } 
}
</script>
