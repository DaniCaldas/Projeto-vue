<template>
<div class="container" style="text-align: center;">
    <h1>Registro</h1>
    <FormTodo v-on:add-todo="Logar"></FormTodo>
    
       <h2>Seus dados </h2>
       <div class="list-group">
        <div class="list-group-item" v-for="(dadosdousuario, index) in dados" v-bind:key="index">
            <p>{{dadosdousuario.Nome}}</p>
            <p>{{dadosdousuario.Telefone}}</p>
            <p>{{dadosdousuario.email}}</p>
            <a href="#" v-on:click.prevent="Removerdados(index)">Excluir</a>
        </div>
        </div>
</div> 
</template>


<script>
import FormTodo from './FormTodo.vue';
export default{
    components:{
        FormTodo
    },
       data(){
     return{
            dados:[],
            }
        },
        methods:{
            Logar(dadosdousuario){
                this.dados.push(dadosdousuario);
            },
            Removerdados(index){
                this.dados.splice(index, 1)
                console.log(Date.now(),this.dados) 
            },
        }
}
</script>
<style>
</style>