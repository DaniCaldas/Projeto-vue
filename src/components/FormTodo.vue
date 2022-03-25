<template>
       <br>
       <div >
       <h4>Nome</h4>
       <input class="input-name" type="text" v-model="Nome">
       
       <br> <br>

       <h4>Telefone

       </h4>
       <input class="input-number" type="text" placeholder="(00)0000-0000"  v-model='Telefone'>
       <br> <br>
    </div>
       <h4>E-mail</h4>
        <input type="email" class="input-email" placeholder="exemple@gmail.com" v-model="email">
       <br><br>

       <button class="btn-primary" v-on:click="Logar">Submit</button>

       <br>
       <br>

</template>

<style scoped>
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

.input-number:hover{
    cursor: pointer;
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
                if(this.Nome=='' && this.Nome==0 && this.Telefone=='' || this.Telefone == String && this.email=='' || this.email.length != '@gmail.com' ) {
                    window.alert('Dados inválidos')
                    this.Nome=''
                    this.Telefone=''
                    this.email=''
                }else{

                //método para mostrar os dados diretamente ao clicar no botão
                this.$emit('add-todo',{
                    Nome:this.Nome,
                    Telefone:this.Telefone,
                    email:this.email
                });
                    this.Nome=''
                    this.Telefone=''
                    this.email=''
            }
        }

        } 
}
</script>
