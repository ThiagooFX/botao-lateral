<template>
  <div class="hello">
    <div class="container">
      <div class="elemento2" id="elemento2">
        <button id="seta" @click="largura" v-if="ativo == false">@</button>
        <button id="seta" @click="voltar" v-if="ativo == true">@</button>
      </div>
      <div class="elemento1" id="elemento1">Mensagem teste na barra do botão</div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'botaocrescente',
    data(){
      return{
        ativo: false
      }
    },
    methods:{
      largura(){
        const larg = document.getElementById("elemento1");
        larg.style.width = "500px";
        this.ativo = !this.ativo
      },
      voltar(){
        const larg = document.getElementById("elemento1");
        larg.style.width = "0px";
        this.ativo = !this.ativo
      }
    }

  }
</script>

<style scoped>
  .container{
    display: flex;
    float: right;
  }
  #elemento1{
    height: 100px;
    width: 0px;
    background-color: #08b363;
    transition: 1.5s;
    overflow: hidden;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  #elemento2{
    height: 100px;
    width: 100px;
    background-color: #08b363;
    transition: 1s;
    border-top-left-radius: 50%;
    border-bottom-left-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  #seta{
    border: none;
    border-radius: 50%;
    height: 100px;
    width: 100px;
    scale: .7;
    font-weight: bold;
    font-size: xx-large;
    cursor: pointer;
    transition: 1.5s;
  }

</style>
